---
title: Chart (control)
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VST.ProjectItem.ExcelChart
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Chart control [Office development in Visual Studio], events
- Chart control [Office development in Visual Studio]
- Chart control [Office development in Visual Studio], data binding
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 864422aac695fbf474e6ed6b8cf6d765247eabf9
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71255301"
---
# <a name="chart-control"></a>Chart (control)
  El control <xref:Microsoft.Office.Tools.Excel.Chart> es un objeto de gráfico que expone eventos. Al agregar un gráfico a una hoja de cálculo, Visual Studio crea un objeto <xref:Microsoft.Office.Tools.Excel.Chart> que se puede programar directamente sin tener que recorrer el modelo de objetos de Microsoft Office Excel.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="create-the-control"></a>Crear el control
 Puede agregar controles <xref:Microsoft.Office.Tools.Excel.Chart> a una hoja de cálculo de Microsoft Office Excel en tiempo de diseño o en tiempo de ejecución en un proyecto de nivel de documento.

 Puede agregar controles <xref:Microsoft.Office.Tools.Excel.Chart> a una hoja de cálculo en tiempo de ejecución en un complemento de VSTO. Para obtener más información, vea [Cómo: Agregar controles Chart a hojas de](../vsto/how-to-add-chart-controls-to-worksheets.md)cálculo.

> [!NOTE]
> Los objetos de gráfico creados de forma dinámica no se conservan en la hoja de cálculo como controles host cuando se cierra la hoja de cálculo. Para obtener más información, vea [Agregar controles a documentos de Office en tiempo de ejecución](../vsto/adding-controls-to-office-documents-at-run-time.md).

## <a name="formatting"></a>Formato
 Todo el formato que se puede aplicar a un control <xref:Microsoft.Office.Interop.Excel.Chart> también puede aplicarse a un control <xref:Microsoft.Office.Tools.Excel.Chart>. Esto incluye bordes, fuentes, tipo de gráfico, líneas de cuadrícula, leyenda y etiquetas de datos.

## <a name="events"></a>Eventos
 Los eventos siguientes están disponibles para el control <xref:Microsoft.Office.Tools.Excel.Chart> :

- <xref:Microsoft.Office.Tools.Excel.Chart.ActivateEvent>

- <xref:Microsoft.Office.Tools.Excel.Chart.BeforeDoubleClick>

- <xref:Microsoft.Office.Tools.Excel.Chart.BeforeRightClick>

- <xref:Microsoft.Office.Tools.Excel.Chart.BindingContextChanged>

- <xref:Microsoft.Office.Tools.Excel.Chart.Calculate>

- <xref:Microsoft.Office.Tools.Excel.Chart.Deactivate>

- <xref:System.ComponentModel.Component.Disposed>

- <xref:Microsoft.Office.Tools.Excel.Chart.DragOver>

- <xref:Microsoft.Office.Tools.Excel.Chart.DragPlot>

- <xref:Microsoft.Office.Tools.Excel.Chart.MouseDown>

- <xref:Microsoft.Office.Tools.Excel.Chart.MouseMove>

- <xref:Microsoft.Office.Tools.Excel.Chart.MouseUp>

- <xref:Microsoft.Office.Tools.Excel.Chart.Resize>

- <xref:Microsoft.Office.Tools.Excel.Chart.SelectEvent>

- <xref:Microsoft.Office.Tools.Excel.Chart.SeriesChange>

## <a name="see-also"></a>Vea también
- [Ejemplos y tutoriales de desarrollo de Office](../vsto/office-development-samples-and-walkthroughs.md)
- [Ampliar documentos de Word y libros de Excel en complementos de VSTO en tiempo de ejecución](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)
- [Controles en documentos de Office](../vsto/controls-on-office-documents.md)
- [Agregar controles a documentos de Office en tiempo de ejecución](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [Automatizar Excel usando objetos extendidos](../vsto/automating-excel-by-using-extended-objects.md)
- [Cómo: Agregar controles Chart a hojas de cálculo](../vsto/how-to-add-chart-controls-to-worksheets.md)
- [Enlazar datos a controles en soluciones de Office](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Limitaciones de programación de elementos y controles host](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
