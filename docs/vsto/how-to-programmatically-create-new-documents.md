---
title: Procedimiento Crear nuevos documentos mediante programación
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- templates [Office development in Visual Studio], custom document
- Word [Office development in Visual Studio], creating documents
- documents [Office development in Visual Studio], creating
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 71610d0bd2e957d932e31d83d06aca914bf8b585
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71251961"
---
# <a name="how-to-programmatically-create-new-documents"></a>Procedimiento Crear nuevos documentos mediante programación
  Al crear un documento mediante programación, el nuevo documento es un objeto <xref:Microsoft.Office.Interop.Word.Document> nativo. Este objeto no tiene los eventos y capacidades de enlace de datos adicionales de un elemento host <xref:Microsoft.Office.Tools.Word.Document>. Para obtener más información, vea [limitaciones de programación de elementos y controles host](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

 Al desarrollar un proyecto de nivel de documento, no se pueden agregar elementos host <xref:Microsoft.Office.Tools.Word.Document> al proyecto mediante programación. En un proyecto de complemento de VSTO, puede convertir cualquier objeto <xref:Microsoft.Office.Interop.Word.Document> en un elemento host <xref:Microsoft.Office.Tools.Word.Document> en tiempo de ejecución. Para obtener más información, vea [ampliar documentos de Word y libros de Excel en complementos de VSTO en tiempo de ejecución](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).

## <a name="to-create-a-new-document-based-on-the-normal-template"></a>Para crear un documento nuevo basado en la plantilla Normal

- Use el método <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> de la colección <xref:Microsoft.Office.Interop.Word.Documents> para crear un nuevo documento basado en la plantilla Normal. Para usar este ejemplo de código, ejecútelo desde la clase `ThisDocument` o `ThisAddIn` del proyecto.

     [!code-vb[Trin_VstcoreWordAutomation#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#1)]
     [!code-csharp[Trin_VstcoreWordAutomation#1](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#1)]

## <a name="use-custom-templates"></a>Usar plantillas personalizadas
 El <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> método tiene un argumento de *plantilla* opcional para crear un nuevo documento basado en una plantilla distinta de la plantilla normal. Debe proporcionar el nombre de archivo y la ruta de acceso completa de la plantilla.

### <a name="to-create-a-new-document-based-on-a-custom-template"></a>Para crear un documento nuevo basado en una plantilla personalizada

- Llame al método <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> de la colección <xref:Microsoft.Office.Interop.Word.Documents> y especifique la ruta de acceso a la plantilla. Para usar este ejemplo de código, ejecútelo desde la clase `ThisDocument` o `ThisAddIn` del proyecto.

     [!code-vb[Trin_VstcoreWordAutomation#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#2)]
     [!code-csharp[Trin_VstcoreWordAutomation#2](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#2)]

## <a name="see-also"></a>Vea también
- [Cómo: Abrir documentos existentes mediante programación](../vsto/how-to-programmatically-open-existing-documents.md)
- [Información general sobre elementos y controles host](../vsto/host-items-and-host-controls-overview.md)
- [Limitaciones de programación de elementos y controles host](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
- [Parámetros opcionales en las soluciones de Office](../vsto/optional-parameters-in-office-solutions.md)
