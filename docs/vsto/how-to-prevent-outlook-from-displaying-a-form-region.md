---
title: 'Cómo: impedir que Outlook muestre un área de formulario'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], canceling display
- canceling form region display
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 90da255beb0a85a302158feb1f9d5cc4981437eb
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "85520139"
---
# <a name="how-to-prevent-outlook-from-displaying-a-form-region"></a>Cómo: impedir que Outlook muestre un área de formulario
  Puede haber situaciones en las que no desee que Microsoft Office Outlook muestre un área de formulario para un elemento determinado. Por ejemplo, si un elemento de contacto no contiene una dirección de negocio, puede impedir que aparezca un área de formulario que muestre la ubicación de la empresa en un mapa.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="to-prevent-outlook-from-displaying-a-form-region"></a>Para impedir que Outlook muestre un área de formulario

1. Abra el archivo de código del área de formulario que desea modificar.

2. Expanda la región de código **generador de áreas de formulario** .

3. Agregue código al `FormRegionInitializing` controlador de eventos que establezca la <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> propiedad de la <xref:Microsoft.Office.Tools.Outlook.FormRegionInitializingEventArgs> clase en **true**.

   En este ejemplo, si el elemento Contact no contiene una dirección, la <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> propiedad se establece en **true**y el área de formulario no aparece.

## <a name="example"></a>Ejemplo
 [!code-csharp[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Separate_O12/MapIt.cs#1)]
 [!code-vb[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Separate_O12/MapIt.vb#1)]

## <a name="see-also"></a>Consulte también
- [Crear áreas de formulario de Outlook](../vsto/creating-outlook-form-regions.md)
- [Tutorial: diseñar un área de formulario de Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md)
- [Cómo: agregar un área de formulario a un proyecto de complemento de Outlook](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)
- [Tutorial: diseñar un área de formulario de Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md)
- [Tutorial: importar un área de formulario diseñada en Outlook](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)
