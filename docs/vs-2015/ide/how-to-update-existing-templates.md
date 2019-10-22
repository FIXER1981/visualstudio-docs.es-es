---
title: Procedimiento Actualizar plantillas existentes | Documentos de Microsoft
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- item templates, updating existing templates
- Visual Studio templates, updating existing templates
- project templates, updating existing templates
ms.assetid: d585e45b-7fe2-45fa-9cf3-7f2bc060f3c4
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 26482e844a4850efb1c50b15e51e4153baf1f9ab
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "68186262"
---
# <a name="how-to-update-existing-templates"></a>Procedimiento Actualización de plantillas existentes
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Después de crear una plantilla y comprimir los archivos en un archivo .zip, es posible que desee modificarla. Puede hacerlo al cambiar los archivos de la misma de forma manual o al exportar una nueva plantilla de un proyecto basado en la plantilla.  
  
## <a name="using-the-export-template-wizard-to-update-an-existing-template"></a>Utilizar el Asistente para exportar plantillas para actualizar una plantilla existente  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Proporciona un **Exportar plantilla** asistente que puede usarse para actualizar una plantilla existente.  
  
#### <a name="to-use-export-template-to-update-an-existing-template"></a>Para usar Exportar plantilla para actualizar una plantilla existente  
  
1. En el menú **Archivo** , haga clic en **Nuevo** y, a continuación, en **Nuevo proyecto**.  
  
2. Seleccione la plantilla que desea actualizar, escriba un nombre y una ubicación para el proyecto temporal y haga clic en **Aceptar**.  
  
3. Modifique el proyecto en [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
4. En el **archivo** menú, haga clic en **Exportar plantilla**y usar el **Exportar plantilla** Asistente para crear una nueva plantilla.  
  
5. Una vez comprimida la plantilla actualizada en un archivo .zip, elimine el archivo .zip de plantilla anterior.  
  
## <a name="manually-updating-an-existing-template"></a>Actualizar manualmente una plantilla existente  
 Puede actualizar una plantilla existente fuera de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] si modifica los archivos del archivo .zip comprimido.  
  
#### <a name="to-manually-update-an-existing-template"></a>Para actualizar manualmente una plantilla existente  
  
1. Busque el archivo .zip que contiene la plantilla. De forma predeterminada, este archivo se encuentra en Documents\Visual Studio *versión*\My Exported Templates\\.  
  
2. Extraiga el archivo .zip.  
  
3. Modifique o elimine los archivos de plantilla actuales, o agregue nuevos archivos a la plantilla.  
  
4. Abra, modifique y guarde el archivo XML .vstemplate para controlar el comportamiento actualizado o los nuevos archivos. Para obtener más información sobre el esquema .vstemplate, vea [Visual Studio Template Schema Reference](../extensibility/visual-studio-template-schema-reference.md) (Referencia de esquema de plantillas de Visual Studio). Para obtener más información sobre lo que se puede parametrizar en los archivos de origen, consulte [parámetros de plantilla](../ide/template-parameters.md)  
  
5. Seleccione los archivos en la plantilla, haga clic en, haga clic en **enviar a**y, a continuación, haga clic en **carpeta comprimida (zip)** . Los archivos seleccionados se comprimen en un archivo .zip.  
  
6. Coloque el nuevo archivo .zip en el mismo directorio que el antiguo.  
  
7. Elimine los archivos de plantilla extraídos y el archivo .zip de plantilla antiguo.  
  
8. Iniciar (como administrador) una instancia de la línea de comandos para desarrolladores (en el menú Inicio, en **Visual Studio 2010 o Visual Studio Tools/Developer Command Prompt**).  
  
9. Ejecute el comando siguiente: `devenv /installvstemplates`.  
  
## <a name="see-also"></a>Vea también  
 [Personalizar plantillas](../ide/customizing-project-and-item-templates.md)   
 [Crear plantillas para proyectos y elementos en Visual Studio](../ide/creating-project-and-item-templates.md)   
 [Referencia de esquema de plantillas de Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Parámetros de plantilla](../ide/template-parameters.md)   
 [Cómo: crear Starter Kits](../ide/how-to-create-starter-kits.md)
