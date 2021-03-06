---
title: Solución de problemas de errores del cliente Docker en Windows | Microsoft Docs
description: Solucione los problemas que encuentre al usar Visual Studio para crear e implementar aplicaciones web en Docker en Windows mediante Visual Studio.
ms.technology: vs-azure
author: ghogen
manager: jillfra
ms.custom: seodec18
ms.assetid: 346f70b9-7b52-4688-a8e8-8f53869618d3
ms.devlang: dotnet
ms.topic: troubleshooting
ms.workload: multiple
ms.date: 01/27/2020
ms.author: ghogen
ms.openlocfilehash: 31b9d8649abed0f9901aa872ff3939c25e3025b8
ms.sourcegitcommit: 9a7fb8556a5f3dbb4459122fefc7e7a8dfda753a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2020
ms.locfileid: "87235113"
---
# <a name="troubleshoot-visual-studio-development-with-docker"></a>Solución de problemas de desarrollo de Visual Studio con Docker

Al trabajar con las herramientas de contenedor de Visual Studio, se pueden producir problemas al compilar o depurar la aplicación. A continuación, se especifican algunos pasos comunes de solución de problemas.

## <a name="volume-sharing-is-not-enabled-enable-volume-sharing-in-the-docker-ce-for-windows-settings--linux-containers-only"></a>El uso compartido de volúmenes no está habilitado. Habilite el uso compartido de volúmenes en la configuración de Docker CE para Windows (solo en contenedores con Linux)

Para resolver este problema, haga lo siguiente:

1. Haga clic derecho en **Docker para Windows** en el área de notificación y, a continuación, seleccione **Configuración**.
1. Seleccione **Shared Drives** (Unidades compartidas) y comparta la unidad del sistema con la unidad donde reside el proyecto.

> [!NOTE]
> Si los archivos aparecen compartidos, puede que deba hacer clic en el vínculo "Reset credentials..." (Restablecer credenciales...) en la parte inferior del cuadro de diálogo para volver a habilitar el uso compartido de volúmenes. Para continuar después de restablecer las credenciales, es posible que deba reiniciar Visual Studio.

![unidades compartidas](media/troubleshooting-docker-errors/shareddrives.png)

> [!TIP]
> Las versiones de Visual Studio posteriores a la versión 15.6 de Visual Studio 2017 preguntan cuando las **unidades compartidas** no están configuradas.

### <a name="container-type"></a>Tipo de contenedor

Al agregar compatibilidad con Docker a un proyecto, se elige un contenedor de Linux o Windows. El host de Docker debe ejecutar el mismo tipo de contenedor. Para cambiar el tipo de contenedor en la instancia de Docker en ejecución, haga clic con el botón derecho en el icono de Docker en la bandeja del sistema y elija **Switch to Windows containers...** (Cambiar a contenedores Windows) o **Switch to Linux containers...** (Cambiar a contenedores Linux).

## <a name="unable-to-start-debugging"></a>No se puede iniciar la depuración

Una razón podría estar relacionada con tener componentes de depuración obsoletos en la carpeta del perfil del usuario. Ejecute los comandos siguientes para quitar estas carpetas, a fin de que se descarguen los últimos componentes de depuración en la siguiente sesión de depuración.

- del %userprofile%\vsdbg
- del %userprofile%\onecoremsvsmon

## <a name="errors-specific-to-networking-when-debugging-your-application"></a>Errores específicos de redes al depurar una aplicación

Intente ejecutar el script que puede descargar de [Cleanup Container Host Networking](https://github.com/MicrosoftDocs/Virtualization-Documentation/tree/master/windows-server-container-tools/CleanupContainerHostNetworking) (Limpieza de redes host de contenedores), que actualizará los componentes de red en el equipo host.

## <a name="mounts-denied"></a>Montajes denegados

Al usar Docker para macOS, podría encontrar un error que haga referencia a la carpeta /usr/local/share/dotnet/sdk/NuGetFallbackFolder. Agregue la carpeta a la pestaña Uso compartido de archivos de Docker.

## <a name="docker-users-group"></a>Grupo de usuarios de Docker

Podría aparecer el siguiente error en Visual Studio al trabajar con contenedores:

```
The current user must be in the 'docker-users' group to use Docker Desktop. 
Add yourself to the 'docker-users' group and then log out of Windows.
```

Debe ser miembro del grupo "docker-users" para obtener permisos para trabajar con contenedores de Docker.  Para agregarse al grupo en Windows 10, siga estos pasos:

1. En el menú Inicio, abra **Administración de equipos**.
1. Expanda **Grupos y usuarios locales** y seleccione **Grupos**.
1. Busque el grupo **docker-users**, haga clic con el botón derecho y seleccione **Agregar a grupo**.
1. Agregue la cuenta o cuentas de usuario.
1. Cierre la sesión y vuelva a iniciarla para que estos cambios surtan efecto.

También puede usar el comando `net localgroup` en el símbolo del sistema del administrador para agregar usuarios a grupos determinados.

```cmd
net localgroup docker-users DOMAIN\username /add
```

En PowerShell, use la función [Add-LocalGroupMember](/powershell/module/microsoft.powershell.localaccounts/add-localgroupmember).

## <a name="low-disk-space"></a>Espacio de disco bajo

De forma predeterminada, Docker almacena imágenes en la carpeta *%ProgramData%/Docker/* , que normalmente se encuentra en la unidad del sistema, *C:\ProgramData\Docker\*. Para evitar que las imágenes ocupen espacio valioso en la unidad del sistema, puede cambiar la ubicación de la carpeta de imágenes.  Desde el icono de Docker en la barra de tareas, abra la configuración de Docker, elija **Demonio** y cambie de **Básico** a **Avanzado**. En el panel de edición, agregue la configuración de la propiedad `graph` con el valor de la ubicación deseada para las imágenes de Docker:

```json
    "graph": "D:\\mypath\\images"
```

![Captura de pantalla de la configuración de ubicación de las imágenes de Docker](media/troubleshooting-docker-errors/docker-settings-image-location.png)

Haga clic en **Aplicar** para reiniciar Docker. En estos pasos se modifica el archivo de configuración que se encuentra en *%ProgramData%\docker\config\daemon.json*. Las imágenes compiladas previamente no se mueven.

## <a name="microsoftdockertools-github-repo"></a>Repositorio de GitHub de Microsoft/DockerTools

Para otros problemas que detecte, consulte los problemas de [Microsoft/DockerTools](https://github.com/microsoft/dockertools/issues).

## <a name="see-also"></a>Consulte también

- [Solución de problemas de Visual Studio](/troubleshoot/visualstudio/welcome-visual-studio/)