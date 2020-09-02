---
title: 'Cómo: comprobar la ortografía en hojas de cálculo mediante programación'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- spellchecking
- spelling checker, worksheets
- worksheets, checking spelling
- spelling, checking in worksheets
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 797fc498c54bdbc466fe8ddc35229b2c106db80d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "85541549"
---
# <a name="how-to-programmatically-check-spelling-in-worksheets"></a>Cómo: comprobar la ortografía en hojas de cálculo mediante programación
  Puede comprobar la ortografía en una hoja de cálculo mediante programación. El cuadro de diálogo **Ortografía** aparece automáticamente si hay palabras mal escritas en la hoja de cálculo.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="to-check-spelling-in-a-worksheet-in-a-document-level-customization"></a>Para revisar la ortografía en una hoja de cálculo en una personalización de nivel de documento

1. Llame al método <xref:Microsoft.Office.Tools.Excel.Worksheet.CheckSpelling%2A> de la hoja de cálculo.

     [!code-csharp[Trin_VstcoreExcelAutomation#45](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#45)]
     [!code-vb[Trin_VstcoreExcelAutomation#45](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#45)]

## <a name="to-check-spelling-in-a-worksheet-in-a-vsto-add-in"></a>Para revisar la ortografía en una hoja de cálculo en un complemento de VSTO

1. Llame al método <xref:Microsoft.Office.Interop.Excel._Worksheet.CheckSpelling%2A> de la hoja de cálculo activa.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#22](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#22)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#22](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#22)]

## <a name="see-also"></a>Consulte también
- [Trabajar con hojas de cálculo](../vsto/working-with-worksheets.md)
- [Cómo: ejecutar cálculos de Excel mediante programación](../vsto/how-to-programmatically-run-excel-calculations-programmatically.md)
- [NamedRange (control)](../vsto/namedrange-control.md)
- [Parámetros opcionales en las soluciones de Office](../vsto/optional-parameters-in-office-solutions.md)
