---
title: Procedimiento Crear un documento XML basado en un esquema XSD
ms.date: 11/04/2016
ms.topic: how-to
ms.assetid: 193b195f-e918-4c79-a1a1-8096a1433bde
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 799d27716e7ab2dd621dce04375093f4aff375d7
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "88893364"
---
# <a name="how-to-create-an-xml-document-based-on-an-xsd-schema"></a>Procedimiento Creación de un documento XML basado en un esquema XSD

La característica **Generar XML de ejemplo** genera un archivo XML de ejemplo a partir del archivo de esquema XML (XSD).

Puede usar esta opción en los escenarios siguientes:

- Si desea comprender el uso de varias construcciones en un esquema dado.

- Confirmar que el esquema hace aquello que estaba previsto.

La característica **Generar XML de ejemplo** solo está disponible en los elementos globales y requiere un conjunto de esquemas XML válido.

Esta característica suele generar documentos XML válidos. Sin embargo, si el esquema contiene uno o varios de los siguientes elementos, la muestra podría no ser válida:

- Las restricciones de identidad `xs:key`, `xs:keyref` y `xs:unique`.

- Facetas `xs:pattern`.

- Enumeraciones del tipo `xs:QName`.

- Los tipos `xs:ENTITY`, `xs:ENTITIES` y `xs:NOTATION`.

Además, observe que el contenido de `xs:base64Binary` solo se generará si aparecen enumeraciones en el esquema para ese tipo.

## <a name="to-generate-an-xml-instance-document-based-on-the-xsd-file"></a>Para generar un documento de instancia XML basado en el archivo XSD

1. Siga los pasos que se describen en [Procedimientos: Creación y edición de un archivo de esquema XSD](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).

2. En el [Explorador de esquemas XML](../xml-tools/xml-schema-explorer.md), haga clic con el botón derecho en el elemento global `PurchaseOrder` y, después, seleccione **Generar XML de ejemplo**.

     Al seleccionar esta opción, se generará el archivo PurchaseOrder.*xml* con el contenido XML de ejemplo siguiente y se abrirá en el editor XML:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <PurchaseOrder OrderDate="1900-01-01" xmlns="http://tempuri.org/PurchaseOrderSchema.xsd">
      <ShipTo country="US">
        <name>name1</name>
        <street>street1</street>
        <city>city1</city>
        <state>state1</state>
        <zip>1</zip>
      </ShipTo>
      <ShipTo country="US">
        <name>name2</name>
        <street>street2</street>
        <city>city2</city>
        <state>state2</state>
        <zip>-79228162514264337593543950335</zip>
      </ShipTo>
      <BillTo country="US">
        <name>name1</name>
        <street>street1</street>
        <city>city1</city>
        <state>state1</state>
        <zip>1</zip>
      </BillTo>
    </PurchaseOrder>
    ```
