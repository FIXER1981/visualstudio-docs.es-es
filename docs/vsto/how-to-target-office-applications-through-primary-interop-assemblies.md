---
title: Procedimiento Aplicaciones de Office de destino a través de los ensamblados de interoperabilidad primarios
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- assemblies [Office development in Visual Studio], PIA references
- primary interop assemblies [Office development in Visual Studio], adding references to
- Office primary interop assemblies in Visual Studio, adding references to
- Office applications [Office development in Visual Studio], automating
- application development [Office development in Visual Studio], automating
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 02a69cb91a24b60e8161948a650a6993a634b665
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "63421038"
---
# <a name="how-to-target-office-applications-through-primary-interop-assemblies"></a>Procedimiento Aplicaciones de Office de destino a través de los ensamblados de interoperabilidad primarios
  Cuando se crea un nuevo proyecto de Office, Visual Studio agrega automáticamente las referencias a los ensamblados de interoperabilidad primarios (PIA) de Microsoft Office necesarios para compilar el proyecto. Debe agregar referencias a otros PIA en los escenarios siguientes:

- Desea usar las características de otras aplicaciones de Microsoft Office en su proyecto. Por ejemplo, quizás le interese usar las características de Microsoft Office Excel en un proyecto de Microsoft Office Word.

- Desea automatizar las aplicaciones de Microsoft Office que no tienen proyectos dedicados en Visual Studio, como Microsoft Office Access.

  [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

  [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

## <a name="to-add-a-reference-to-a-primary-interop-assembly"></a>Para agregar una referencia a un ensamblado de interoperabilidad primario

1. Abra el proyecto de Office y seleccione el nombre del proyecto en **el Explorador de soluciones**.

2. En el menú **Proyecto**, haga clic en **Agregar referencia**.

3. En el **Framework** pestaña, seleccione el PIA que desee en el **nombre del componente** lista. Para obtener más información acerca de los ensamblados de interoperabilidad primarios disponibles de Microsoft Office, consulte [ensamblados de interoperabilidad primarios de Office](../vsto/office-primary-interop-assemblies.md).

     Si el proyecto tiene como destino el [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] o versiones posteriores, el **Embed Interop Types** propiedad para la referencia de ensamblado está establecida en **True** de forma predeterminada. Con esta configuración, la solución no requiere el PIA en los equipos de los usuarios finales. Para obtener más información, consulte [diseño y crear soluciones de Office](../vsto/designing-and-creating-office-solutions.md).

    > [!NOTE]
    > En los proyectos de Office, agregue siempre referencias a los PIA de Office mediante el uso de la **.NET** pestaña de la **Agregar referencia** cuadro de diálogo en lugar de **COM** ficha. Para obtener más información, consulte [ensamblados de interoperabilidad primarios de Office](../vsto/office-primary-interop-assemblies.md).

4. Haga clic en **Aceptar**.

     El nombre del ensamblado aparece en la **referencias** carpeta de **el Explorador de soluciones**.

## <a name="see-also"></a>Vea también
- [Ensamblados de interoperabilidad primarios de Office](../vsto/office-primary-interop-assemblies.md)
- [Escribir código en soluciones de Office](../vsto/writing-code-in-office-solutions.md)
- [Desarrollar soluciones de Office](../vsto/developing-office-solutions.md)
- [Cómo: Instalar a ensamblados de interoperabilidad primarios de Office](../vsto/how-to-install-office-primary-interop-assemblies.md)
