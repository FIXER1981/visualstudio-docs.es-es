---
title: Copiar datos y formato en hojas de cálculo mediante programación
titleSuffix: ''
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, copying data
- formatting [Office development in Visual Studio]
- data [Office development in Visual Studio], copying across worksheets
- copying data, Office development in Visual Studio
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e72d7c94068e5fe9ca0bf533d9d8fe4b7f8e8e54
ms.sourcegitcommit: 9d2829dc30b6917e89762d602022915f1ca49089
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2020
ms.locfileid: "91585267"
---
# <a name="how-to-programmatically-copy-data-and-formatting-across-worksheets"></a>Cómo: copiar datos y formato en hojas de cálculo mediante programación
  Puede copiar los datos de un rango de una hoja a todas las demás hojas de un libro mediante el <xref:Microsoft.Office.Interop.Excel.Worksheets.FillAcrossSheets%2A> método. Especifique un intervalo y si desea copiar los datos, el formato o ambos.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="example"></a>Ejemplo
 [!code-csharp[Trin_VstcoreExcelAutomation#44](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#44)]
 [!code-vb[Trin_VstcoreExcelAutomation#44](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#44)]

## <a name="compile-the-code"></a>Compilar el código
 Este ejemplo requiere un intervalo denominado `rangeData` en una hoja de cálculo.

## <a name="see-also"></a>Vea también
- [Trabajar con hojas de cálculo](../vsto/working-with-worksheets.md)
- [Cómo: agregar nuevas hojas de cálculo a libros mediante programación](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)
- [Cómo: cambiar el formato en filas de hojas de cálculo que contienen celdas seleccionadas mediante programación](../vsto/how-to-programmatically-change-formatting-in-worksheet-rows-containing-selected-cells.md)
- [Parámetros opcionales en las soluciones de Office](../vsto/optional-parameters-in-office-solutions.md)
