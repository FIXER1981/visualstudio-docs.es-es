---
title: Guía del administrador de Visual Studio | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-install
ms.topic: conceptual
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
ms.assetid: 4af353f5-6cfd-4ebe-bcfb-f42306e451a0
caps.latest.revision: 76
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: a59f9f2cb2548d6d40670832e66d4df5c83680df
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "74295914"
---
# <a name="visual-studio-administrator-guide"></a>Visual Studio Administrator Guide
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Para obtener la documentación más reciente sobre Visual Studio, vea la [Guía del administrador de Visual Studio](/visualstudio/install/visual-studio-administrator-guide).

Puede implementar Visual Studio 2015 en una red siempre y cuando cada equipo de destino cumpla los [requisitos mínimos de instalación](https://visualstudio.microsoft.com/vs/older-downloads/). Para crear un recurso compartido de red, puede ejecutar el archivo de instalación con el modificador -layout (como se describe en la página [Crear una instalación sin conexión de Visual Studio](../install/create-an-offline-installation-of-visual-studio.md)) y, después, copiarlo desde el equipo al recurso compartido de red. Si usa una imagen ISO, puede montar la imagen ISO y compartirla o copiar la imagen ISO en un recurso compartido de red.  
  
 Tenga en cuenta que las instalaciones que se realizan desde un recurso compartido de red "recuerdan" la ubicación de la que proceden. Esto significa que, para reparar un equipo cliente, quizás sea necesario volver al recurso compartido de red desde el que se instaló el cliente. Elija cuidadosamente la ubicación de red para que esté disponible durante el tiempo que espera que los clientes de Visual Studio 2015 se ejecuten en su organización.  
  
## <a name="detection-and-servicing-keys"></a>Claves de detección y servicio  
 Se pueden utilizar las subclaves de detección del Registro para determinar si un producto de Visual Studio ya está instalado en un equipo. Para determinar si es necesario continuar con una instalación, usaría estas claves de detección en una implementación automatizada.  Consulte [detectar requisitos del sistema](../extensibility/internals/detecting-system-requirements.md)[detectar requisitos del sistema].  
  
## <a name="avoiding-reboots"></a>Evitar reinicios  
 Para reducir los reinicios, asegúrese de que se cumplen los requisitos previos de Visual Studio antes de implementar Visual Studio. En el .NET Framework, es posible que tenga que reiniciar los equipos que ejecutan Windows 8 Si implementa Visual Studio 2015 en ellos sin instalar primero el .NET Framework 4,6.  
  
 Para la emulación de dispositivos Windows y Android, quizás tenga que reiniciar los equipos si aún no tiene activada la característica Hyper-V de Windows. Para el desarrollo web, puede que necesite reiniciar los equipos si aún no tiene activada la característica Servidor Web de Windows. Para el desarrollo de Office, puede que necesite reiniciar los equipos si aún no tiene activada la característica Windows Identify Foundation de Windows. reiniciar los equipos si aún no tiene activada la característica Servidor Web de Windows. Para el desarrollo de Office, puede que necesite reiniciar los equipos si aún no tiene activada la característica Windows Identify Foundation de Windows. Para más información sobre cómo automatizar la detección e instalación de las características de Windows, consulte [Instalar un rol de servidor en un servidor que ejecuta una instalación Server Core de Windows Server 2008 R2](https://technet.microsoft.com/library/ee441260(v=ws.10).aspx).  
  
## <a name="error-return-codes"></a>Códigos de retorno de error  
 En la siguiente tabla figuran importantes códigos de error. Puede usar estos códigos de error en la automatización para decidir si es necesario reiniciar el equipo y si la instalación se realizó correctamente. Si recibe un código de error, tenga en cuenta los pasos de solución de problemas en la página [instalar Visual Studio](../install/install-visual-studio-2015.md) .  
  
|Estado de la instalación|Reinicio no necesario|Reinicio necesario|Descripción|  
|------------------|--------------------------|----------------------|-----------------|  
|Correcto|0x00000000 [0]|0x00000bc2 [3010]|Instalación correcta.|  
|Bloquear|0x80044000 [-2147205120]|0x8004C000 [-2147172352]|Si el único bloque que se notifica es “Reinicio pendiente”, el valor devuelto es Incompleto-Reinicio necesario (0x80048bc7).|  
|Cancelar|0x00000642 [1602]|0x80048642 [-2147187134]|Cuando se devuelve el valor Reinicio, el Código de retorno es 1602.|  
|Incompleto-Reinicio necesario|N/D|0x80048bc7 [-2147185721]|El reinicio es necesario para poder continuar con la instalación.|  
|Error|0x00000643 [1603]|0x80048643 [-2147187133]|Cuando se devuelve el valor Reinicio, el Código de retorno es 1603.|  
  
## <a name="interactive-administrator-installer"></a>Instalador de administrador interactivo  
 Si va a crear a un instalador interactivo sobre la instalación de Visual Studio, puede ver el progreso desde el instalador de Visual Studio. El instalador de Visual Studio 2015 se basa en la tecnología de encadenador de Windows Installer XML (WiX) de código abierto, también conocida como Burn. La tecnología de grabación admite dos protocolos de comunicación: burn y netfx4. Para obtener una referencia breve, vea la descripción del atributo Protocol en la documentación del elemento del exepackage en [wixtoolset.org](https://wixtoolset.org/). Se puede requerir una revisión de la implementación de código abierto de WiX de este atributo de protocolo para la integración.  
  
## <a name="controlling-what-is-installed"></a>Controlar lo que se instala  
 Si quiere controlar lo que el usuario final puede instalar, hay dos opciones: la instalación de archivos de administrador y las opciones de línea de comandos. Si su objetivo es restringir lo que el usuario final puede elegir en su experiencia de Visual Studio, seleccione la instalación de archivos de administrador. Si quiere crear una configuración inicial y permitir que el usuario final elija su propia experiencia de Visual Studio, seleccione los parámetros de línea de comandos.  
  
 Para más información sobre la experiencia de archivo del administrador, vea [How to: Create and Run an Unattended Installation of Visual Studio](../install/how-to-create-and-run-an-unattended-installation-of-visual-studio.md) y [How to: Automatically apply product keys when deploying Visual Studio](../install/how-to-automatically-apply-product-keys-when-deploying-visual-studio.md).  Para obtener más información sobre los controles de línea de comandos, vea la página [usar parámetros de la línea de comandos para instalar Visual Studio](../install/use-command-line-parameters-to-install-visual-studio.md) .  
  
## <a name="specifying-customer-feedback-settings"></a>Especificar valores de comentarios de clientes  

De manera predeterminada, la instalación de Visual Studio permite recibir comentarios de los clientes. Puede configurar Visual Studio para deshabilitar los comentarios de los clientes en los equipos individuales si cambia el valor de la siguiente clave del Registro a la cadena "0":  
  
**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\VisualStudio\SQM**  
**OptIn**  
  
(Por ejemplo, cámbielo a HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\VisualStudio\SQM OptIn = "0")  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Cómo: Instalar una versión específica de Visual Studio](../install/how-to-install-a-specific-release-of-visual-studio.md)|Describe cómo instalar configuraciones específicas de la versión actual de  [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] .|  
|[Cómo: Crear y ejecutar una instalación desatendida de Visual Studio](../install/how-to-create-and-run-an-unattended-installation-of-visual-studio.md)|Describe cómo instalar [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] en modo desatendido.|  
|[Cómo: Aplicar automáticamente las claves de producto durante la implementación de Visual Studio](../install/how-to-automatically-apply-product-keys-when-deploying-visual-studio.md)|Describe cómo aplicar claves de producto al implementar en varios equipos.|  
|[Guía del administrador del Visor de Ayuda](../ide/help-viewer-administrator-guide.md)|Proporciona información sobre cómo administrar instalaciones de ayuda local para entornos de red que tienen o no tienen acceso a Internet.|  
|[Instalación de Visual Studio](../install/install-visual-studio-2015.md)|Proporciona instrucciones y vínculos a temas en los que se describe cómo instalar [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] .|