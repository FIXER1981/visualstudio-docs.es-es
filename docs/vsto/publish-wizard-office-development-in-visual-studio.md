---
title: Asistente para publicación (desarrollo de Office en Visual Studio)
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VST.ProjectProperties.PublishWizard
- VST.PublishWizard.Publish.2007System
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ClickOnce deployment [Office development in Visual Studio], Publish Wizard
- deploying applications [Office development in Visual Studio], Publish Wizard
- Office applications [Office development in Visual Studio], Publish Wizard
- Publish Wizard, Office solutions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 9ce0be90be111d458229189c2a06624bd726ac05
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56604846"
---
# <a name="publish-wizard-office-development-in-visual-studio"></a>Asistente para publicación (desarrollo de Office en Visual Studio)
  Use la **Asistente para publicación** para copiar los archivos de solución en una ubicación especificada, crear los archivos de manifiesto y crear un programa de instalación.

 Para obtener acceso a este asistente, en el **compilar** menú, elija **publicar** *SolutionName*. También puede tener acceso a la **Asistente para publicación** desde **el Explorador de soluciones**. Abra el menú contextual del nodo de proyecto y, a continuación, elija **publicar**.

 Cada sección siguiente describe una página del asistente.

## <a name="where-do-you-want-to-publish-the-application"></a>¿Dónde desea publicar la aplicación?
 **Especifique la ubicación para publicar esta aplicación** necesarios. La ubicación de publicación es el directorio donde la **Asistente para publicación** copia los archivos de solución, como los manifiestos, los ensamblados, certificados temporales y otros archivos de la compilación. Es necesario tener acceso de escritura a este directorio.

 Escriba la ubicación como una ruta de acceso de disco, recurso compartido de archivos, sitios FTP o dirección URL del sitio web, o haga clic en el **examinar** botón para buscar la ubicación. La ruta de acceso puede estar en estos formatos:

- Una ruta de acceso relativa o absoluta en el estándar de Windows de formato, como *C:\Deploy\MyApplication* o *\MyApplication*.

- Una ruta de acceso de convención de nomenclatura Universal (UNC), como  *\\\ServerName\MyApplication\\*.

- Una dirección URL de un sitio web de sitio, como http://www.microsoft.com/MyApplication.

  De forma predeterminada, la ubicación de publicación es *http://localhost/projectname/* si tiene IIS instalado, o el directorio publish\ si tiene IIS instalado.

> [!NOTE]
>  Hay varias consideraciones si el equipo de destino se está ejecutando Windows Vista. Debe ser un administrador en el equipo de Windows Vista para usar la opción de publicación local. Además, la ubicación predeterminada es siempre el *publicar\\*  directorio, independientemente de si tiene IIS instalado.

## <a name="what-is-the-default-installation-path-on-end-user-computers"></a>¿Qué es la ruta de instalación predeterminada en los equipos del usuario final?
 La ruta de instalación es opcional. Puede establecer la ruta de instalación más adelante si lo prefiere. Para obtener más detalles, vea [Cómo: Cambiar la ruta de instalación de una solución de Office](https://msdn.microsoft.com/d0eaa07b-2d72-4902-899f-2f9fb165b8fd).

 La ruta de instalación es el directorio desde el que el usuario final instalará la personalización. También es la ruta de acceso que usará la solución para buscar actualizaciones. El **Asistente para publicación** implementar la solución a esta ubicación, a menos que la ruta de acceso es el mismo que el especificado en el **especificar la ubicación para publicar esta aplicación** cuadro en la página anterior.

 **Desde un sitio Web** especificar la dirección URL que los usuarios finales seguirán para instalar la solución.

 **Desde un recurso compartido de archivo o ruta de acceso UNC** especificar la ruta de acceso UNC que los usuarios finales seguirán para instalar la solución.

 **Desde un CD-ROM o DVD-ROM** esta opción no requiere una ruta de instalación.

 Visual Studio no grabar el CD o DVD. Debe copiar manualmente el resultado en un CD o DVD.

## <a name="see-also"></a>Vea también
- [Implementar una solución de Office mediante ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md)
- [Panel publicar, Diseñador de proyectos &#40;desarrollo de Office en Visual Studio&#41;](../vsto/publish-page-project-designer-office-development-in-visual-studio.md)
- [Implementar una solución de Office](../vsto/deploying-an-office-solution.md)
