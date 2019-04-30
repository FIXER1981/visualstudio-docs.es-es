---
title: NamedRange (control)
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VST.Toolbox.Range
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, named
- NamedRange control, events
- NamedRange control, data binding
- NamedRange control
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8dd8627c4e9baaa790a5d97a8021220a820356fb
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "63442434"
---
# <a name="namedrange-control"></a>NamedRange (control)
  El control <xref:Microsoft.Office.Tools.Excel.NamedRange> es un rango que tiene un nombre único, expone eventos y se puede enlazar a datos. Para obtener más información, consulte [información general sobre el modelo de objetos de Excel](../vsto/excel-object-model-overview.md).

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="create-the-control"></a>Crear el control
 Puede agregar controles <xref:Microsoft.Office.Tools.Excel.NamedRange> a una hoja de cálculo de Microsoft Office Excel en tiempo de diseño o en tiempo de ejecución en un proyecto de nivel de documento.

 Puede agregar controles <xref:Microsoft.Office.Tools.Excel.NamedRange> a una hoja de cálculo en tiempo de ejecución en un complemento de VSTO. Para obtener más información, vea [Cómo: Agregar controles NamedRange a hojas de cálculo](../vsto/how-to-add-namedrange-controls-to-worksheets.md).

> [!NOTE]
> Los rangos con nombre creados de forma dinámica no se conservan en la hoja de cálculo como controles host cuando esta se cierra. Para obtener más información, consulte [agregar controles a documentos de Office en tiempo de ejecución](../vsto/adding-controls-to-office-documents-at-run-time.md).

 Los controles<xref:Microsoft.Office.Tools.Excel.NamedRange> solo pueden tener rangos en hojas específicas. Los controles<xref:Microsoft.Office.Tools.Excel.NamedRange> no pueden tener nombres relativos que se aplican a todas las hojas, ni pueden componerse de rangos que abarquen dos o más hojas de cálculo en un libro (rangos 3D).

## <a name="bind-data-to-the-control"></a>Enlazar datos al control
 Un rango con nombre parece ser un buen candidato para enlaces de datos complejos, ya que puede contener muchas celdas; sin embargo, un rango es simplemente una colección de celdas que no se puede asignar fácilmente a una columna concreta desde un conjunto de datos. Por lo tanto, los controles <xref:Microsoft.Office.Tools.Excel.NamedRange> solo admiten el enlace de datos simple. El control <xref:Microsoft.Office.Tools.Excel.ListObject> se puede utilizar para el enlace de datos complejos. Para obtener más información, consulte [control ListObject](../vsto/listobject-control.md).

 El control <xref:Microsoft.Office.Tools.Excel.NamedRange> puede estar enlazado a un origen de datos utilizando las propiedades de <xref:System.Windows.Forms.Control.DataBindings%2A> . La propiedad de enlace de datos predeterminada del control <xref:Microsoft.Office.Tools.Excel.NamedRange> es <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A>.

 Si los datos del conjunto de datos enlazado se actualizan mediante cualquier mecanismo, el control <xref:Microsoft.Office.Tools.Excel.NamedRange> refleja los cambios.

## <a name="formatting"></a>Formato
 El formato que puede aplicarse a un control <xref:Microsoft.Office.Interop.Excel.Range> también puede aplicarse a un control <xref:Microsoft.Office.Tools.Excel.NamedRange> . Esto incluye bordes, fuentes, los formatos de número y estilos.

## <a name="rename-the-control"></a>Cambie el nombre del control
 Cuando se agrega un control <xref:Microsoft.Office.Tools.Excel.NamedRange> a la hoja de cálculo desde el **Cuadro de herramientas**, Visual Studio genera automáticamente un nombre para el control. Puede cambiar este nombre en la ventana **Propiedades** .

## <a name="events"></a>Eventos
 Los eventos siguientes están disponibles para el control <xref:Microsoft.Office.Tools.Excel.NamedRange> :

- <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeDoubleClick>

- <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeRightClick>

- <xref:Microsoft.Office.Tools.Excel.NamedRange.BindingContextChanged>

- <xref:Microsoft.Office.Tools.Excel.NamedRange.Change>

- <xref:Microsoft.Office.Tools.Excel.NamedRange.Deselected>

- <xref:System.ComponentModel.Component.Disposed>

- <xref:Microsoft.Office.Tools.Excel.NamedRange.Selected>

- <xref:Microsoft.Office.Tools.Excel.NamedRange.SelectionChange>

## <a name="see-also"></a>Vea también
- [Automatizar Excel usando objetos extendidos](../vsto/automating-excel-by-using-extended-objects.md)
- [Tutoriales y ejemplos de desarrollo de office](../vsto/office-development-samples-and-walkthroughs.md)
- [Enlazar datos a controles en soluciones de Office](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Extender documentos de Word y libros de Excel en complementos VSTO en tiempo de ejecución](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)
- [Controles en documentos de Office](../vsto/controls-on-office-documents.md)
- [Agregar controles a documentos de Office en tiempo de ejecución](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [Cómo: Agregar controles NamedRange a hojas de cálculo](../vsto/how-to-add-namedrange-controls-to-worksheets.md)
- [Cómo: Cambiar el tamaño de los controles NamedRange](../vsto/how-to-resize-namedrange-controls.md)
- [Enlazar datos a controles en soluciones de Office](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Tutorial: Programar basándose en eventos de un control NamedRange](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)
- [Limitaciones de programación de elementos host y controles host](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
