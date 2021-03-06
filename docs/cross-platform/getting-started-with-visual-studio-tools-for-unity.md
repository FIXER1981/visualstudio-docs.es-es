---
title: Introducción a Visual Studio Tools para Unity | Microsoft Docs
description: Introducción a Visual Studio Tools para Unity. Instale Visual Studio, configure Unity para su empleo con Visual Studio y obtenga información sobre la compatibilidad con versiones anteriores.
ms.custom: ''
ms.date: 05/11/2020
ms.technology: vs-unity-tools
ms.topic: how-to
ms.assetid: 66b5b4eb-13b5-4071-98d2-87fafa4598a8
author: indiesaudi
ms.author: crdun
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: 223458a448a4b32c3e9480f7189d5dc636ce8375
ms.sourcegitcommit: 01c1b040b12d9d43e3e8ccadee20d6282154faad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2020
ms.locfileid: "92039456"
---
# <a name="get-started-with-visual-studio-tools-for-unity"></a>Introducción a Visual Studio Tools para Unity

## <a name="install-visual-studio"></a>Instalar Visual Studio

### <a name="unity-bundled-installation"></a>Instalación agrupada de Unity

A partir de Unity 2018.1, Visual Studio es el editor de scripts predeterminado de C# para Unity y se incluye en el Asistente para la descarga de Unity, así como la herramienta de instalación de Unity Hub.

- Descargue Unity desde [store.unity.com](https://store.unity.com/).

Durante la instalación, asegúrese de que Visual Studio está activado en la lista de componentes que quiere instalar con Unity:

#### <a name="unity-hub"></a>Unity Hub

:::moniker range="vs-2017"
![Instalación de Unity Hub](media/vs-2017/vstu-unity-hub.png)
:::moniker-end
:::moniker range=">=vs-2019"
![Instalación de Unity Hub](media/vs-2019/vstu-unity-hub.png)
:::moniker-end

:::moniker range="vs-2017"

#### <a name="unity-download-assistant"></a>Asistente para la descarga de Unity

![Instalación del Asistente para la descarga de Unity](media/vs-2017/vstu-download-assistant.png)

Es posible que la versión de Visual Studio incluida con la instalación de Unity no sea la más reciente. Si se le pide que instale Visual Studio 2017, se recomienda instalar manualmente una versión más reciente de Visual Studio.
:::moniker-end

### <a name="manual-installation"></a>Instalación manual

Si ya tiene instalado Visual Studio, o prefiere instalarlo manualmente, ejecute el instalador de Visual Studio.

1. [Descargue el instalador de Visual Studio](../install/install-visual-studio.md) o ábralo si ya está instalado.

1. Haga clic en **Modificar** (si ya está instalado) o en **Instalar** (si es una nueva instalación) para la versión de Visual Studio que prefiera.

1. En la pestaña **Cargas de trabajo** , desplácese a la sección **Mobile & Gaming** (Móvil y juegos) y seleccione la carga de trabajo **Game development with Unity** (Desarrollo de juegos con Unity).

   :::moniker range="vs-2017"
   ![Carga de trabajo de Unity](media/vs-2017/vstu-unity-workload.png)
   :::moniker-end
   :::moniker range=">=vs-2019"
   ![Carga de trabajo de Unity](media/vs-2019/vstu-unity-workload.png)
   :::moniker-end

1. Haga clic en **Modificar** (si ya está instalada) o en **Instalar** (si es una nueva instalación) en la esquina inferior derecha de la ventana del instalador.

#### <a name="check-for-updates-to-visual-studio"></a>Búsqueda de actualizaciones para Visual Studio

Se recomienda comprobar las actualizaciones en Visual Studio para asegurarse de que tiene acceso a las herramientas y características más recientes. Esto no interrumpirá el proyecto de Unity.

- [Actualizar Visual Studio](../install/update-visual-studio.md)

## <a name="configure-unity-for-use-with-visual-studio"></a>Configuración de Unity para su uso con Visual Studio

A partir de Unity 2018.1, Visual Studio debe ser el editor de scripts externos predeterminado en Unity. Puede confirmarlo o cambiar el editor de scripts externo a una versión específica de Visual Studio:

1. Seleccione **Preferencias** en el menú **Editar** .

   :::moniker range="vs-2017"
   ![Selección de Preferencias](media/vs-2017/vstu-unity-preferences.png)
   :::moniker-end
   :::moniker range=">=vs-2019"
   ![Selección de Preferencias](media/vs-2019/vstu-unity-preferences.png)
   :::moniker-end

2. En el cuadro de diálogo Preferencias, seleccione la pestaña **Herramientas externas** .

3. En la lista desplegable **External Script Editor** (Editor de scripts externo), elija la versión deseada de Visual Studio si aparece en la lista; de lo contrario, seleccione **Examinar...** .

   :::moniker range="vs-2017"
   ![Selección de Visual Studio](media/vs-2017/vstu-unity-external-tools.png)
   :::moniker-end
   :::moniker range=">=vs-2019"
   ![Selección de Visual Studio](media/vs-2019/vstu-unity-external-tools.png)
   :::moniker-end

4. Si **Examinar...** estaba seleccionado, vaya al directorio **Common7/IDE** dentro del directorio de instalación de Visual Studio y seleccione **devenv.exe** . A continuación, haga clic en **Abrir** .

   :::moniker range="vs-2017"
   ![Selección de Abrir](media/vs-2017/vstu-browse-for-application.png)
   :::moniker-end
   :::moniker range=">=vs-2019"
   ![Selección de Abrir](media/vs-2019/vstu-browse-for-application.png)
   :::moniker-end

5. Después de que Visual Studio se ha seleccionado en la lista **External Script Editor** (Editor de scripts externo), confirme que la casilla **Editor Attaching** (Asociación de editor) está activada.

6. Cierre el cuadro de diálogo **Preferencias** para completar el proceso de configuración.

## <a name="support-for-older-versions"></a>Compatibilidad con versiones anteriores

Descargue e instale Visual Studio Tools para Unity desde Visual Studio Marketplace. Deberá instalar el paquete adecuado para su versión de Visual Studio.

- Para Visual Studio 2015 Community, Visual Studio 2015 Professional o Visual Studio 2015 Enterprise:

   [Descargar Visual Studio 2015 Tools para Unity](https://marketplace.visualstudio.com/items?itemName=SebastienLebreton.VisualStudio2015ToolsforUnity)

> [!NOTE]
> Visual Studio Tools para Unity requiere Unity 5.2 y posterior, así como una versión de Visual Studio que admita extensiones, como Visual Studio Community, Professional, Premium o Enterprise. Para comprobar que Visual Studio Tools para Unity está habilitado en la instalación de Unity, seleccione **About Unity** (Acerca de Unity) en el menú **Ayuda** y busque el texto "Microsoft Visual Studio Tools para Unity habilitado" en la parte inferior izquierda del cuadro de diálogo.
> ![Acerca de Unity](media/vs-2019/vstu-about-unity.png)

## <a name="next-steps"></a>Pasos siguientes

 Para obtener información sobre el uso y la depuración de su proyecto Unity en Visual Studio, vea [Visual Studio Tools para Unity](../cross-platform/using-visual-studio-tools-for-unity.md).
