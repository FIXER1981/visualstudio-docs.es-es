---
title: Publicar aplicaciones ClickOnce | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.Dialog.Options
- Microsoft.VisualStudio.Publish.ClickOnceProvider.PublishWizard.Help
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, publishing
- ClickOnce applications, publishing
- applications [Visual Studio], ClickOnce deployment
- deploying applications [ClickOnce], publishing ClickOnce applications
ms.assetid: eb6dfe79-f54c-4331-8e36-073688e70973
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b46b1b5fa7952fbd1a14dc9eca7f67c493ea2807
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62928537"
---
# <a name="publish-clickonce-applications"></a>Publicación de aplicaciones ClickOnce
Cuando se publica una aplicación [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] por primera vez, las propiedades de publicación se pueden establecer con el Asistente para publicación. Sólo algunas de las propiedades están disponibles en el asistente; todas las restantes se establecen en sus valores predeterminados.

 Los cambios posteriores en las propiedades de publicación se realizan en el panel **Publicar** del **Diseñador de proyectos**.

## <a name="publish-wizard"></a>Asistente para publicación
 Puede utilizar el Asistente para publicación para definir la configuración básica de la publicación. Incluye las siguientes propiedades de publicación:

- Ubicación de la carpeta de publicación: es la ubicación donde Visual Studio va a copiar los archivos (equipo local, recurso compartido de archivos de la red, servidor FTP o sitio web).

- Ubicación de la carpeta de instalación: es la ubicación desde donde los usuarios finales van a realizar la instalación (recurso compartido de archivos de la red, servidor FTP, sitio web, CD/DVD)

- Disponibilidad en línea o sin conexión: determina si los usuarios pueden obtener acceso a la aplicación con o sin conexión a la red.

- Frecuencia de actualización: define la frecuencia con la que la aplicación comprueba si hay nuevas actualizaciones.

  Para obtener más información, vea [Cómo: Publicación de una aplicación ClickOnce mediante el Asistente para publicación](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).

## <a name="publish-page"></a>Página Publicar
 La página **Publicar** del **Diseñador de proyectos** se utiliza para configurar las propiedades para la implementación de ClickOnce. En la tabla siguiente figuran algunos temas.

|Título|Descripción|
|-----------|-----------------|
|[Cómo: Especificación de la ubicación en la que Visual Studio copia los archivos](../deployment/how-to-specify-where-visual-studio-copies-the-files.md)|Describe cómo establecer la ubicación donde Visual Studio copia los archivos de aplicación y los manifiestos.|
|[Cómo: Especificación de la ubicación desde la que instalarán los usuarios finales](../deployment/how-to-specify-the-location-where-end-users-will-install-from.md)|Describe cómo establecer la ubicación desde donde los usuarios van a descargar e instalar la aplicación.|
|[Cómo: Especificación del modo de instalación en línea y sin conexión de ClickOnce](../deployment/how-to-specify-the-clickonce-offline-or-online-install-mode.md)|Describe cómo establecer si la aplicación estará disponible sin conexión o en línea.|
|[Cómo: Establecimiento de la versión de publicación de ClickOnce](../deployment/how-to-set-the-clickonce-publish-version.md)|Describe cómo establecer la propiedad **Versión de publicación** de ClickOnce, que determina si la aplicación que se está publicando se tratará o no como una actualización.|
|[Cómo: Incremento automático de la versión de publicación de ClickOnce](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)|Describe cómo incrementar automáticamente el número de revisión de la **Versión de publicación** cada vez que se publica la aplicación.|

 Para obtener más información, consulte [página Publicar, Diseñador de proyectos](../ide/reference/publish-page-project-designer.md)

### <a name="application-files-dialog-box"></a>Cuadro de diálogo Archivos de aplicación
 Este cuadro de diálogo le permite especificar cómo se organizan en categorías los archivos de su proyecto para la publicación, la descarga dinámica y la actualización. Contiene una cuadrícula que muestra los archivos de proyecto que no se excluyen de manera predeterminada o que tienen un grupo de descarga.

 Para excluir archivos, marcarlos como archivos de datos o requisitos previos y crear grupos de archivos para la instalación condicional en la interfaz de usuario de Visual Studio, vea [ Cómo: Especificar los archivos que se van a publicar mediante ClickOnce](../deployment/how-to-specify-which-files-are-published-by-clickonce.md). Los archivos de datos también se pueden marcar mediante la herramienta Mage.exe. Para obtener más información, vea [Cómo: Inclusión de un archivo de datos en una aplicación ClickOnce](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md).

### <a name="prerequisites-dialog-box"></a>Cuadro de diálogo Requisitos previos
 Este cuadro de diálogo especifica qué componentes necesarios se instalan y cómo se instalan. Para obtener más información, vea [Cómo: Instalar requisitos previos mediante una aplicación ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md) y [cuadro de diálogo de requisitos previos](../ide/reference/prerequisites-dialog-box.md).

### <a name="application-updates-dialog-box"></a>Cuadro de diálogo Actualizaciones de la aplicación
 Este cuadro de diálogo especifica cómo debe comprobar la instalación de la aplicación si hay actualizaciones. Para obtener más información, vea [Cómo: Administración de actualizaciones de aplicaciones ClickOnce](../deployment/how-to-manage-updates-for-a-clickonce-application.md).

### <a name="publish-options-dialog-box"></a>Cuadro de diálogo Opciones de publicación
 El cuadro de diálogo Opciones de publicación especifica las opciones de implementación de una aplicación.

|||
|-|-|
|[Cómo: Cambio del idioma de publicación de una aplicación ClickOnce](../deployment/how-to-change-the-publish-language-for-a-clickonce-application.md)|Describe cómo especificar un idioma y una referencia cultural para la versión localizada.|
|[Cómo: Especificar un nombre de menú Inicio para una aplicación ClickOnce](../deployment/how-to-specify-a-start-menu-name-for-a-clickonce-application.md)|Describe cómo cambiar el nombre para mostrar de una aplicación ClickOnce.|
|[Cómo: Especificación de un vínculo para soporte técnico](../deployment/how-to-specify-a-link-for-technical-support.md)|Describe cómo establecer la propiedad **URL de soporte**, que identifica una página web o un recurso compartido de archivos donde los usuarios pueden obtener información sobre la aplicación.|
|[Cómo: Especificación de una dirección URL de soporte para requisitos previos individuales en una implementación ClickOnce](../deployment/how-to-specify-a-support-url-for-individual-prerequisites-in-a-clickonce-deployment.md)|Explica cómo modificar manualmente un manifiesto de aplicación para incluir las direcciones URL de soporte de cada requisito previo.|
|[Cómo: Especificación de una página de publicación para una aplicación ClickOnce](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)|Describe cómo generar y publicar una página web predeterminada (publish.htm) junto con la aplicación.|
|[Cómo: Personalización de la página web predeterminada para ClickOnce](../deployment/how-to-customize-the-default-web-page-for-a-clickonce-application.md)|Describe cómo personalizar la página web que se genera y se publica automáticamente junto con la aplicación.|
|[Cómo: Habilitar AutoStart para instalaciones con CD](../deployment/how-to-enable-autostart-for-cd-installations.md)|Describe cómo habilitar Autoinicio para que la aplicación ClickOnce se inicie automáticamente cuando se inserta el disco.|

## <a name="related-topics"></a>Temas relacionados

|Título|Descripción|
|-----------|-----------------|
|[Cómo: Creación de asociaciones de archivo para una aplicación ClickOnce](../deployment/how-to-create-file-associations-for-a-clickonce-application.md)|Describe cómo agregar a una aplicación ClickOnce compatibilidad con extensiones de nombre de archivo.|
|[Cómo: Recuperación de información de la cadena de consulta de una aplicación ClickOnce en línea](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md)|Muestra cómo recuperar los parámetros pasados a la dirección URL utilizada para ejecutar una aplicación ClickOnce.|
|[Cómo: Desactivación de la activación de URL de aplicaciones ClickOnce mediante el diseñador](../deployment/how-to-disable-url-activation-of-clickonce-applications-by-using-the-designer.md)|Describe cómo obligar a los usuarios a iniciar la aplicación desde el menú **Inicio** mediante el diseñador.|
|[Cómo: Desactivación de la activación de URL de aplicaciones ClickOnce](../deployment/how-to-disable-url-activation-of-clickonce-applications.md)|Describe cómo obligar a los usuarios a iniciar la aplicación desde el menú **Inicio**.|
|[Tutorial: Descarga de ensamblados a petición con la API de implementación ClickOnce mediante el diseñador](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer.md)|Explica cómo descargar los ensamblados de aplicación solo cuando la aplicación los utiliza por primera vez mediante el diseñador.|
|[Tutorial: Descargar ensamblados a petición con la API de implementación de ClickOnce](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api.md)|Explica cómo descargar los ensamblados de aplicación sólo cuando la aplicación los utiliza por primera vez.|
|[Tutorial: Descargar ensamblados satélite a petición con la API de implementación de ClickOnce](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md)|Describe cómo marcar los ensamblados satélite como opcionales y descargar únicamente el ensamblado que un equipo cliente necesite para la configuración de su referencia cultural actual.|
|[Tutorial: Implementar manualmente una aplicación ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)|Explica cómo utilizar las utilidades de .NET Framework para implementar su aplicación ClickOnce.|
|[Tutorial: Implementar manualmente una aplicación ClickOnce que no requiere volver a firmar y que conserve la información de personalización de marca](../deployment/walkthrough-manually-deploying-a-clickonce-app-no-re-signing-required.md)|Explica cómo utilizar las utilidades de .NET Framework para implementar la aplicación ClickOnce sin volver a firmar los manifiestos.|
|[Cómo: Configurar proyectos para plataformas de destino](../ide/how-to-configure-projects-to-target-platforms.md)|Explica cómo publicar en el caso de un procesador de 64 bits: se cambia la propiedad **CPU de destino** o **Destino de la plataforma** en el proyecto.|
|[Tutorial: Habilitar una aplicación ClickOnce para ejecutarse en varias versiones de .NET Framework](https://msdn.microsoft.com/library/7f4383af-ed87-4853-b4d4-02a3967a5fd9)|Explica cómo habilitar una aplicación ClickOnce para que se instale y se ejecute en varias versiones de .NET Framework.|
|[Tutorial: Crear a un instalador personalizado para una aplicación ClickOnce](../deployment/walkthrough-creating-a-custom-installer-for-a-clickonce-application.md)|Explica cómo crear un instalador personalizado para instalar una aplicación ClickOnce.|
|[Cómo: Publicación de una aplicación WPF con estilos visuales habilitados](../deployment/how-to-publish-a-wpf-application-with-visual-styles-enabled.md)|Proporciona instrucciones paso a paso para resolver un error que se produce al intentar publicar una aplicación WPF que tiene habilitados estilos visuales.|

## <a name="see-also"></a>Vea también
- [Seguridad e implementación ClickOnce](../deployment/clickonce-security-and-deployment.md)
- [Referencia a ClickOnce](../deployment/clickonce-reference.md)
