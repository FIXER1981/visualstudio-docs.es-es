---
title: fragmentos XML
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 348dbf64-3f09-4fff-b47a-a7ecdf3221cc
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a2f2bcdd0c28d7b4b99c92d3346b32ed34aa92a0
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/01/2020
ms.locfileid: "75592326"
---
# <a name="xml-snippets"></a>fragmentos XML

El Editor XML ofrece una característica denominada *fragmentos XML* que permite compilar archivos XML con una mayor rapidez. Los fragmentos XML se pueden reutilizar insertándolos en los archivos. También es posible generar datos XML en un esquema de lenguaje de definición de esquemas XML (XSD).

## <a name="reusable-xml-snippets"></a>Fragmentos XML reutilizables

El Editor XML incluye muchos fragmentos que abarcan algunas tareas comunes. Esto permite crear archivos XML de forma más sencilla. Por ejemplo, si fuera a crear un esquema XML con los fragmentos "Complex Type Sequence Element" y "Simple Type Element", insertaría el texto XML siguiente en el archivo. Luego, cambiaría el valor `name` de acuerdo con sus necesidades.

```xml
<xs:element name="name">
  <xs:complexType>
    <xs:sequence>
      <xs:element name="name">
        <xs:simpleType>
          <xs:restriction base="xs:string"></xs:restriction>
        </xs:simpleType>
      </xs:element>
    </xs:sequence>
  </xs:complexType>
</xs:element>
```

Los fragmentos se pueden insertar de dos maneras. El comando **Insertar fragmento** inserta el fragmento XML en la posición del cursor. El comando **Delimitar con** ajusta el fragmento XML alrededor del texto seleccionado. Ambos comandos están disponibles en el submenú **IntelliSense** del menú **Edición** o en el menú contextual del editor.

Para obtener más información, vea [Cómo: Uso de fragmentos XML](../xml-tools/how-to-use-xml-snippets.md).

## <a name="schema-generated-xml-snippets"></a>Fragmentos XML generados por esquema

Con el Editor XML también es posible generar un fragmento XML desde un esquema XML. Esta característica permite llenar un elemento con elementos XML generados a partir de la información de esquema de ese elemento. Para obtener más información, vea [Cómo: Generación de un fragmento XML a partir de un esquema XML](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md).

## <a name="create-new-xml-snippets"></a>Creación de fragmentos XML

Además de los fragmentos que, de forma predeterminada, se incluyen con Visual Studio, puede crear y utilizar sus propios fragmentos XML. Para obtener más información, vea [Cómo: Creación de fragmentos XML](../xml-tools/how-to-create-xml-snippets.md).

## <a name="see-also"></a>Vea también

- [Fragmentos de código en Visual Studio](../ide/code-snippets.md)
- [Editor XML](../xml-tools/xml-editor.md)
