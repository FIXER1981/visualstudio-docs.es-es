---
title: 'CA2240: Implementar ISerializable correctamente'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2240
- ImplementISerializableCorrectly
helpviewer_keywords:
- CA2240
- ImplementISerializableCorrectly
ms.assetid: cf05936d-0d6c-49ed-a1b4-220032e50b97
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 1a6d9acc3a74505f766fbf9cfe26fc6878fdbb4b
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920043"
---
# <a name="ca2240-implement-iserializable-correctly"></a>CA2240: Implementar ISerializable correctamente

|||
|-|-|
|TypeName|ImplementISerializableCorrectly|
|Identificador de comprobación|CA2240|
|Categoría|Microsoft.Usage|
|Cambio problemático|No trascendental|

## <a name="cause"></a>Causa

Un tipo visible externamente se puede asignar a la <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> interfaz y se cumple una de las condiciones siguientes:

- El tipo hereda pero no invalida el <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> método y el tipo declara los campos de instancia que no están marcados con el <xref:System.NonSerializedAttribute?displayProperty=fullName> atributo.

- El tipo no está sellado y el tipo implementa un <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> método que no es visible externamente y reemplazable.

## <a name="rule-description"></a>Descripción de la regla
Los campos de instancia que se declaran en un tipo <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> que hereda la interfaz no se incluyen automáticamente en el proceso de serialización. Para incluir los campos, el tipo debe implementar el <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> método y el constructor de serialización. Si no se deben serializar los campos, aplique el <xref:System.NonSerializedAttribute> atributo a los campos para indicar explícitamente la decisión.

En los tipos que no están sellados, las <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> implementaciones del método deberían estar visibles externamente. Por lo tanto, los tipos derivados pueden llamar al método y se puede reemplazar.

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones
Para corregir una infracción de esta regla, haga <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> que el método sea visible y se pueda reemplazar y asegúrese de que todos los campos de instancia se incluyen en el proceso <xref:System.NonSerializedAttribute> de serialización o que se marcan explícitamente con el atributo.

## <a name="when-to-suppress-warnings"></a>Cuándo suprimir advertencias
No suprima las advertencias de esta regla.

## <a name="example"></a>Ejemplo
En el ejemplo siguiente se muestran dos tipos serializables que infringen la regla.

[!code-csharp[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/CSharp/ca2240-implement-iserializable-correctly_1.cs)]
[!code-cpp[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/CPP/ca2240-implement-iserializable-correctly_1.cpp)]
[!code-vb[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/VisualBasic/ca2240-implement-iserializable-correctly_1.vb)]

## <a name="example"></a>Ejemplo
En el ejemplo siguiente se corrigen las dos infracciones anteriores proporcionando una implementación reemplazable de <xref:System.Runtime.Serialization.ISerializable.GetObjectData> en la clase Book y proporcionando una implementación de `GetObjectData` en la clase Library.

[!code-cpp[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/CPP/ca2240-implement-iserializable-correctly_2.cpp)]
[!code-csharp[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/CSharp/ca2240-implement-iserializable-correctly_2.cs)]
[!code-vb[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/VisualBasic/ca2240-implement-iserializable-correctly_2.vb)]

## <a name="related-rules"></a>Reglas relacionadas

- [CA2236: Llamar a métodos de clase base en tipos ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)
- [CA2229: implementar constructores de serialización](../code-quality/ca2229-implement-serialization-constructors.md)
- [CA2238: Implementar métodos de serialización correctamente](../code-quality/ca2238-implement-serialization-methods-correctly.md)
- [CA2235: Marcar todos los campos no serializables](../code-quality/ca2235-mark-all-non-serializable-fields.md)
- [CA2237: Marcar tipos ISerializable con SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)
- [CA2239 Proporcionar métodos de deserialización para campos opcionales](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)
- [CA2120: Proteger los constructores de serialización](../code-quality/ca2120-secure-serialization-constructors.md)