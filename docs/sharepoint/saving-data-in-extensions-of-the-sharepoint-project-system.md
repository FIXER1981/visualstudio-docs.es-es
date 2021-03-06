---
title: Guardar datos en extensiones del sistema de proyectos de SharePoint | Microsoft Docs
titleSuffix: ''
ms.date: 02/02/2017
ms.topic: conceptual
helpviewer_keywords:
- SharePoint project items, saving string data
- project items [SharePoint development in Visual Studio], saving string data
- projects [SharePoint development in Visual Studio], saving string data
- SharePoint projects, saving string data
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 30142b9aaec3df7ce0d43845e369eb538533de62
ms.sourcegitcommit: 9d2829dc30b6917e89762d602022915f1ca49089
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2020
ms.locfileid: "91583871"
---
# <a name="save-data-in-extensions-of-the-sharepoint-project-system"></a>Guardar datos en extensiones del sistema de proyectos de SharePoint
  Al extender el sistema de proyectos de SharePoint, puede guardar los datos de cadena que se conservan después de cerrar un proyecto de SharePoint. Los datos suelen estar asociados a un elemento de proyecto concreto o al propio proyecto.

 Si tiene datos que no es necesario conservar, puede Agregar los datos a cualquier objeto del modelo de objetos de herramientas de SharePoint que implementa la <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject> interfaz. Para obtener más información, vea [asociar datos personalizados con extensiones de herramientas de SharePoint](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md).

## <a name="save-data-that-is-associated-with-a-project-item"></a>Guardar datos asociados a un elemento de proyecto
 Si tiene datos que están asociados a un determinado elemento de proyecto de SharePoint, como el valor de una propiedad que se agrega a un elemento de proyecto, puede guardar los datos en el archivo *. spdata* del elemento de proyecto. Para ello, utilice la <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> propiedad de un <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> objeto. Los datos que se agregan a esta propiedad se guardan en el elemento **extensiondata (** en el archivo *. spdata* del elemento de proyecto. Para obtener más información, consulte [elemento extensiondata (](../sharepoint/extensiondata-element.md).

 En el ejemplo de código siguiente se muestra cómo utilizar la <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> propiedad para guardar el valor de una propiedad de cadena que se define en un tipo de elemento de proyecto personalizado de SharePoint. Para ver este ejemplo en el contexto de un ejemplo más extenso, vea [Cómo: agregar una propiedad a un tipo de elemento de proyecto personalizado de SharePoint](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md).

 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#14](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemtypeproperty.vb#14)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#14](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemtypeproperty.cs#14)]

## <a name="save-data-that-is-associated-with-a-project"></a>Guardar datos asociados a un proyecto
 Si tiene datos de nivel de proyecto, como el valor de una propiedad que se agrega a los proyectos de SharePoint, puede guardar los datos en el archivo de proyecto (archivo *. csproj* o *. vbproj* ) o en el archivo de opciones de usuario del proyecto (el archivo *. csproj. User* o *. vbproj. User* ). El archivo que elija para guardar los datos dependerá de cómo desee usar los datos:

- Si desea que los datos estén disponibles para todos los desarrolladores que abran el proyecto de SharePoint, guarde los datos en el archivo del proyecto. Este archivo siempre se protege en las bases de datos de control de código fuente, por lo que los datos de este archivo están disponibles para otros desarrolladores que desprotegen el proyecto.

- Si desea que los datos estén disponibles solo para el desarrollador actual que tiene abierto el proyecto de SharePoint en Visual Studio, guarde los datos en el archivo de opciones de usuario del proyecto. Normalmente, este archivo no se protege en las bases de datos de control de código fuente, por lo que los datos de este archivo no están disponibles para otros desarrolladores que desprotegen el proyecto.

### <a name="save-data-to-the-project-file"></a>Guardar datos en el archivo de proyecto
 Para guardar los datos en el archivo de proyecto, convierta un <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> objeto en un <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage> objeto y, a continuación, use el <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetPropertyValue%2A> método. En el ejemplo de código siguiente se muestra cómo utilizar este método para guardar el valor de una propiedad de proyecto en el archivo de proyecto. Para ver este ejemplo en el contexto de un ejemplo más grande, vea [Cómo: agregar una propiedad a proyectos de SharePoint](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md).

 [!code-vb[SpExt_SPCustomPrjProperty#3](../sharepoint/codesnippet/VisualBasic/customspproperty/customproperty.vb#3)]
 [!code-csharp[SpExt_SPCustomPrjProperty#3](../sharepoint/codesnippet/CSharp/customspproperty/customproperty.cs#3)]

 Para obtener más información sobre cómo convertir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> objetos en otros tipos del modelo de objetos de automatización de Visual Studio o del modelo de objetos de integración, vea [convertir entre tipos de sistema de proyectos de SharePoint y otros tipos de proyectos de Visual Studio](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md).

### <a name="save-data-to-the-project-user-option-file"></a>Guardar datos en el archivo de opciones de usuario del proyecto
 Para guardar los datos en el archivo de opciones de usuario del proyecto, use la <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.ProjectUserFileData%2A> propiedad de un <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> objeto. En el ejemplo de código siguiente se muestra cómo utilizar esta propiedad para guardar el valor de una propiedad del proyecto en el archivo de opciones de usuario del proyecto. Para ver este ejemplo en el contexto de un ejemplo más grande, vea [Cómo: agregar una propiedad a proyectos de SharePoint](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md).

 [!code-vb[SpExt_SPCustomPrjProperty#2](../sharepoint/codesnippet/VisualBasic/customspproperty/customproperty.vb#2)]
 [!code-csharp[SpExt_SPCustomPrjProperty#2](../sharepoint/codesnippet/CSharp/customspproperty/customproperty.cs#2)]

## <a name="see-also"></a>Vea también
- [Extensión del sistema de proyectos de SharePoint](../sharepoint/extending-the-sharepoint-project-system.md)
- [Asociar datos personalizados con las extensiones de herramientas de SharePoint](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)
- [Convertir entre tipos de sistema de proyectos de SharePoint y otros tipos de proyectos de Visual Studio](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)
