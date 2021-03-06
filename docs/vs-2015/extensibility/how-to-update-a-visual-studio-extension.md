---
title: Actualizar una extensión | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- update package
- update extension
- new package version
ms.assetid: 93f79774-7b79-4dd6-94ad-13698f72c257
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0d1464cdd2be79cd93a3e98bcf8769e8f4b8b89f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "90843356"
---
# <a name="how-to-update-a-visual-studio-extension"></a>Actualización de una extensión de Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Puede actualizar una extensión de Visual Studio en el sistema mediante el uso de **extensiones y actualizaciones** para instalar la versión actualizada. Si crea una versión actualizada de una extensión, puede indicarla como actualizada incrementando el número de versión en el manifiesto de VSIX.

 Las actualizaciones se instalan cuando el manifiesto VSIX de la extensión entrante tiene el mismo `ID` que el instalado y un `Version` número mayor. Si el `Version` número es igual o inferior, no se puede instalar el paquete. Si los `ID` valores no coinciden, el paquete que todavía no está instalado se reconoce como una extensión independiente.

 Para ayudar a evitar conflictos durante el desarrollo, se recomienda desinstalar las versiones anteriores de las extensiones en curso, así como desinstalar o deshabilitar cualquier otra extensión potencialmente conflictiva.

### <a name="to-update-an-extension-on-your-system"></a>Para actualizar una extensión en el sistema

1. En el menú **Herramientas**, haga clic en **Extensiones y actualizaciones**.

2. En el panel izquierdo, haga clic en **actualizaciones**.

3. En el panel central, haga clic en la actualización que desea instalar.

     El número de versión de la extensión actualizada se muestra en el panel derecho, junto con otra información.

4. En la parte inferior del panel derecho, haga clic en **Actualizar**.

### <a name="to-publish-an-update-of-an-extension"></a>Para publicar una actualización de una extensión

1. En Visual Studio, abra la solución para la extensión que desea actualizar. Realice los cambios.

    > [!IMPORTANT]
    > No se actualizan automáticamente todas las extensiones de usuario sin firmar. Siempre debe firmar las extensiones.

2. En **Explorador de soluciones**, abra Source. Extension. manifest.

3. En el diseñador de manifiestos, aumente el valor del número en el campo **versión** .

4. Guarde la solución y genérelo.

5. Cargue el nuevo archivo. vsix (en la carpeta \bin\Debug\ del proyecto) en el sitio web de [Visual Studio Marketplace](https://marketplace.visualstudio.com/) .

     Cuando un usuario que tenga una versión anterior de la extensión Abra **extensiones y actualizaciones**, la nueva versión aparecerá en la lista de **actualizaciones** , siempre que la herramienta esté configurada para buscar actualizaciones automáticamente.

     Puede habilitar o deshabilitar la comprobación automática de actualizaciones en la parte inferior del panel **actualizaciones** (**habilitar o deshabilitar la detección automática de actualizaciones disponibles**), que cambia la configuración de **Buscar actualizaciones** en **herramientas/opciones/entorno/extensiones y actualizaciones**.

    > [!NOTE]
    > A partir de Visual Studio 2015 Update 2, puede especificar (en **Herramientas / Opciones / Entorno / Extensiones y actualizaciones**) si quiere actualizaciones automáticas para las extensiones por usuario, todas las extensiones de usuario o ambas (la configuración predeterminada).

## <a name="see-also"></a>Consulte también
 [Anatomía de un paquete VSIX](../extensibility/anatomy-of-a-vsix-package.md) [búsqueda y uso de extensiones de Visual Studio](../ide/finding-and-using-visual-studio-extensions.md)
