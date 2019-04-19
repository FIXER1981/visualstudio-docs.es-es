---
title: 'CA2302: Asegúrese de que se establece BinaryFormatter.Binder antes de llamar a BinaryFormatter.Deserialize'
ms.date: 04/05/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: fb997d8184ea9459b46eee95bfe2863e8c1c6ed0
ms.sourcegitcommit: 0e22ead8234b2c4467bcd0dc047b4ac5fb39b977
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59367293"
---
# <a name="ca2302-ensure-binaryformatterbinder-is-set-before-calling-binaryformatterdeserialize"></a>CA2302: Asegúrese de que se establece BinaryFormatter.Binder antes de llamar a BinaryFormatter.Deserialize

|||
|-|-|
|TypeName|EnsureBinaryFormatterBinderIsSetBeforeCallingBinaryFormatterDeserialize|
|Identificador de comprobación|CA2302|
|Categoría|Microsoft.Security|
|Cambio problemático|No trascendental|

## <a name="cause"></a>Motivo

Un <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType> método de deserialización se llama o se hace referencia y el <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> propiedad puede ser null.

## <a name="rule-description"></a>Descripción de la regla

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

Esta regla busca <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType> referencias, o las llamadas a métodos de deserialización cuando <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> cuando su <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> podría ser null. Si no desea permitir cualquier deserialización con <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> independientemente de la <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> propiedad, deshabilite esta regla y [CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md)y Habilitar regla [CA2300](ca2300-do-not-use-insecure-deserializer-binaryformatter.md).

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones

- Si es posible, use un serializador seguro de en su lugar, y **no permitir que un atacante especificar un tipo arbitrario para deserializar**. Algunos serializadores más seguros incluyen:
  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> -No use nunca <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>. Si debe utilizar a una resolución de tipo, debe restringir tipos deserializados a una lista esperada.
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - NewtonSoft Json.NET - Use TypeNameHandling.None. Si se debe usar otro valor para TypeNameHandling, debe restringir tipos deserializados a una lista esperada.
  - Búferes de protocolo
- Asegúrese de alterar los datos serializados. Después de la serialización, firmar criptográficamente los datos serializados. Antes de deserializar, validar la firma criptográfica. Debe proteger la clave criptográfica de que se revele y debe diseñar para las rotaciones de clave.
- Restringir tipos deserializados. Implementar un personalizado <xref:System.Runtime.Serialization.SerializationBinder?displayProperty=nameWithType>. Antes de deserializar con <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, establezca el <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> propiedad a una instancia de personalizado <xref:System.Runtime.Serialization.SerializationBinder>. En el invalidado <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> método, si el tipo es inesperado, a continuación, produce una excepción.
  - Asegúrese de que todas las rutas de código tienen el <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> conjunto de propiedades.

## <a name="when-to-suppress-warnings"></a>Cuándo Suprimir advertencias

- Es seguro suprimir una advertencia de esta regla si sabe que la entrada es de confianza. Considere la posibilidad de que los flujos de datos y límites de confianza de la aplicación pueden cambiar con el tiempo.
- Es seguro suprimir esta advertencia si ha tomado una de las precauciones anteriores.

## <a name="pseudo-code-examples"></a>Ejemplos de pseudocódigo

### <a name="violation"></a>Infracción

```csharp
using System;
using System.IO;
using System.Runtime.Serialization.Formatters.Binary;

[Serializable]
public class BookRecord
{
    public string Title { get; set; }
    public string Author { get; set; }
    public int PageCount { get; set; }
    public AisleLocation Location { get; set; }
}

[Serializable]
public class AisleLocation
{
    public char Aisle { get; set; }
    public byte Shelf { get; set; }
}

public class ExampleClass
{
    public BinaryFormatter Formatter { get; set; }

    public BookRecord DeserializeBookRecord(byte[] bytes)
    {
        using (MemoryStream ms = new MemoryStream(bytes))
        {
            return (BookRecord) this.Formatter.Deserialize(ms);
        }
    }
}
```

```vb
Imports System
Imports System.IO
Imports System.Runtime.Serialization.Formatters.Binary

<Serializable()>
Public Class BookRecord
    Public Property Title As String
    Public Property Author As String
    Public Property Location As AisleLocation
End Class

<Serializable()>
Public Class AisleLocation
    Public Property Aisle As Char
    Public Property Shelf As Byte
End Class

Public Class ExampleClass
    Public Property Formatter As BinaryFormatter

    Public Function DeserializeBookRecord(bytes As Byte()) As BookRecord
        Using ms As MemoryStream = New MemoryStream(bytes)
            Return CType(Me.Formatter.Deserialize(ms), BookRecord)
        End Using
    End Function
End Class
```

### <a name="solution"></a>Soluciones
```csharp
using System;
using System.IO;
using System.Runtime.Serialization;
using System.Runtime.Serialization.Formatters.Binary;

public class BookRecordSerializationBinder : SerializationBinder
{
    public override Type BindToType(string assemblyName, string typeName)
    {
        // One way to discover expected types is through testing deserialization
        // of **valid** data and logging the types used.

        ////Console.WriteLine($"BindToType('{assemblyName}', '{typeName}')");

        if (typeName == "BookRecord" || typeName == "AisleLocation")
        {
            return null;
        }
        else
        {
            throw new ArgumentException("Unexpected type", "typeName");
        }
    }
}

[Serializable]
public class BookRecord
{
    public string Title { get; set; }
    public string Author { get; set; }
    public int PageCount { get; set; }
    public AisleLocation Location { get; set; }
}

[Serializable]
public class AisleLocation
{
    public char Aisle { get; set; }
    public byte Shelf { get; set; }
}

public class ExampleClass
{
    public BookRecord DeserializeBookRecord(byte[] bytes)
    {
        BinaryFormatter formatter = new BinaryFormatter();
        formatter.Binder = new BookRecordSerializationBinder();
        using (MemoryStream ms = new MemoryStream(bytes))
        {
            return (BookRecord) formatter.Deserialize(ms);
        }
    }
}
```

```vb
Imports System
Imports System.IO
Imports System.Runtime.Serialization
Imports System.Runtime.Serialization.Formatters.Binary

Public Class BookRecordSerializationBinder
    Inherits SerializationBinder

    Public Overrides Function BindToType(assemblyName As String, typeName As String) As Type
        ' One way to discover expected types is through testing deserialization
        ' of **valid** data and logging the types used.

        'Console.WriteLine($"BindToType('{assemblyName}', '{typeName}')")

        If typeName = "BinaryFormatterVB.BookRecord" Or typeName = "BinaryFormatterVB.AisleLocation" Then
            Return Nothing
        Else
            Throw New ArgumentException("Unexpected type", "typeName")
        End If
    End Function
End Class

<Serializable()>
Public Class BookRecord
    Public Property Title As String
    Public Property Author As String
    Public Property Location As AisleLocation
End Class

<Serializable()>
Public Class AisleLocation
    Public Property Aisle As Char
    Public Property Shelf As Byte
End Class

Public Class ExampleClass
    Public Function DeserializeBookRecord(bytes As Byte()) As BookRecord
        Dim formatter As BinaryFormatter = New BinaryFormatter()
        formatter.Binder = New BookRecordSerializationBinder()
        Using ms As MemoryStream = New MemoryStream(bytes)
            Return CType(formatter.Deserialize(ms), BookRecord)
        End Using
    End Function
End Class
```

## <a name="related-rules"></a>Reglas relacionadas

[CA2300: No use deserializador inseguro BinaryFormatter](ca2300-do-not-use-insecure-deserializer-binaryformatter.md)

[CA2301: No llame a BinaryFormatter.Deserialize sin establecer primero BinaryFormatter.Binder](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md)