---
title: 'Cómo: imprimir hojas de cálculo mediante programación'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- printing [Office development in Visual Studio], worksheets
- worksheets, printing
- print preview, worksheets
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b0affdd34ad1cb302beacdc1abc9d02275878afd
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "85537896"
---
# <a name="how-to-programmatically-print-worksheets"></a>Cómo: imprimir hojas de cálculo mediante programación

Puede imprimir cualquier hoja de cálculo de un libro.

[!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="print-a-worksheet-in-a-document-level-customization"></a>Imprimir una hoja de cálculo en una personalización de nivel de documento

### <a name="to-print-a-worksheet"></a>Para imprimir una hoja de cálculo

1. Llame al método `PrintOut` de `Sheet1`, solicite dos copias y obtenga una vista previa del documento antes de imprimirlo.

    [!code-csharp[Trin_VstcoreExcelAutomation#22](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#22)]
    [!code-vb[Trin_VstcoreExcelAutomation#22](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#22)]

   El <xref:Microsoft.Office.Tools.Excel.Worksheet.PrintPreview%2A> método le permite mostrar el objeto especificado en la ventana de **vista previa de impresión** . El siguiente código supone que tiene un elemento host <xref:Microsoft.Office.Tools.Excel.Worksheet> denominado `Sheet1`.

### <a name="to-preview-a-page-before-printing"></a>Para obtener una vista previa de una página antes de imprimirla

1. Llame al método <xref:Microsoft.Office.Tools.Excel.Worksheet.PrintPreview%2A> de la hoja de cálculo.

     [!code-csharp[Trin_VstcoreExcelAutomation#23](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#23)]
     [!code-vb[Trin_VstcoreExcelAutomation#23](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#23)]

## <a name="print-a-worksheet-in-a-vsto-add-in"></a>Imprimir una hoja de cálculo en un complemento de VSTO

### <a name="to-print-a-worksheet"></a>Para imprimir una hoja de cálculo

1. Llame al método <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintOut%2A> de la hoja de cálculo activa, solicite dos copias y obtenga una vista previa del documento antes de imprimirlo.

    [!code-csharp[Trin_VstcoreExcelAutomationAddIn#14](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#14)]
    [!code-vb[Trin_VstcoreExcelAutomationAddIn#14](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#14)]

   El <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintPreview%2A> método le permite mostrar el objeto especificado en la ventana de **vista previa de impresión** .

### <a name="to-preview-a-page-before-printing"></a>Para obtener una vista previa de una página antes de imprimirla

1. Llame al método <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintPreview%2A> de la hoja de cálculo activa.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#15](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#15)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#15](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#15)]

## <a name="see-also"></a>Consulte también

- [Trabajar con hojas de cálculo](../vsto/working-with-worksheets.md)
- [Cómo: comprobar la ortografía en hojas de cálculo mediante programación](../vsto/how-to-programmatically-check-spelling-in-worksheets.md)
- [Elemento host de hoja de cálculo](../vsto/worksheet-host-item.md)
- [Acceso global a objetos en proyectos de Office](../vsto/global-access-to-objects-in-office-projects.md)
- [Parámetros opcionales en las soluciones de Office](../vsto/optional-parameters-in-office-solutions.md)
