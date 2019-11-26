---
title: Asignaciones de puerto del Depurador remoto | Microsoft Docs
ms.custom: ''
ms.date: 05/18/2018
ms.topic: reference
ms.assetid: 238bb4ec-bb00-4c2b-986e-18ac278f3959
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2d99a1aff2c241e81e8914a247d2f6d8981ee273
ms.sourcegitcommit: 9c7d8693108ecd2042a70c04cebe3c44af657baf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2019
ms.locfileid: "74239454"
---
# <a name="remote-debugger-port-assignments"></a>Asignaciones de puertos del depurador remoto
El depurador remoto de Visual Studio se puede ejecutar como una aplicación o como un servicio en segundo plano. Cuando se ejecuta como una aplicación, usa un puerto asignado de forma predeterminada como se muestra a continuación:
::: moniker range=">=vs-2019"
- Visual Studio 2019: 4024
::: moniker-end
- Visual Studio 2017: 4022

- Visual Studio 2015: 4020

- Visual Studio 2013: 4018

- Visual Studio 2012: 4016

En otras palabras, el número de puerto asignado al depurador remoto se incrementa en 2 para cada versión. Puede establecer un número de puerto distinto según desee. Explicaremos cómo establecer números de puerto en una sección posterior.

## <a name="the-remote-debugger-port-on-32-bit-operating-systems"></a>Puerto del depurador remoto en sistemas operativos de 32 bits

::: moniker range=">=vs-2019"
 El puerto TCP 4024 (en Visual Studio 2019) es el puerto principal y es necesario en todos los escenarios. Puede configurar este puerto desde la línea de comandos o en la ventana del depurador remoto.
::: moniker-end
::: moniker range="vs-2017"
 El puerto TCP 4022 (en Visual Studio 2017) es el puerto principal y el necesario para todos los escenarios. Puede configurar este puerto desde la línea de comandos o en la ventana del depurador remoto.
::: moniker-end

 En la ventana del depurador remoto, haga clic en **Herramientas > Opciones** y establezca el número de puerto TCP/IP.

 En la línea de comandos, inicie el depurador remoto con el conmutador **/port**: **msvsmon /port\< número de puerto>** .

 Puede encontrar información sobre todos los conmutadores de la línea de comandos del depurador remoto en la ayuda de depuración remota (presione **F1** o haga clic en **Ayuda <Uso** en la ventana del depurador remoto).

## <a name="the-remote-debugger-port-on-64-bit-operating-systems"></a>Puerto del depurador remoto en sistemas operativos de 64 bits
::: moniker range=">=vs-2019"
 Cuando se inicia la versión de 64 bits del Depurador remoto, usa de forma predeterminada el puerto principal (4024).  Si depura un proceso de 32 bits, la versión de 64 bits del Depurador remoto inicia una versión de 32 bits del Depurador remoto en el puerto 4025 (el número de puerto principal incrementado en 1). Si ejecuta el depurador remoto de 32 bits, se usa el puerto 4024 y no el 4025.
::: moniker-end
::: moniker range="vs-2017"
 Cuando se inicia la versión de 64 bits del Depurador remoto, usa de forma predeterminada el puerto principal (4022).  Si depura un proceso de 32 bits, la versión de 64 bits del Depurador remoto inicia una versión de 32 bits del Depurador remoto en el puerto 4023 (el número de puerto principal incrementado en 1). Si ejecuta el depurador remoto de 32 bits, usa el puerto 4022 y no usa el puerto 4023.
:::moniker-end

 Este puerto se puede configurar desde la línea de comandos: **Msvsmon /wow64port \<número de puerto>** .

## <a name="the-discovery-port"></a>Puerto de detección
 UDP 3702 se usa para buscar instancias en ejecución del depurador remoto en la red (por ejemplo, el cuadro de diálogo **Buscar** en el cuadro de diálogo **Asociar al proceso** ). Se usa solo para detectar una máquina que ejecute el depurador remoto, por lo que es opcional si tiene alguna otra manera de conocer el nombre del equipo o la dirección IP del equipo de destino. Se trata de un puerto estándar para la detección, por lo que no es posible configurar el número de puerto.

 Si no desea habilitar la detección, puede iniciar msvsmon desde la línea de comandos con la detección deshabilitada:  **Msvsmon /nodiscovery**.

## <a name="remote-debugger-ports-on-azure"></a>Puertos del depurador remoto en Azure
 El depurador remoto en Azure usa los puertos siguientes. Los puertos del servicio en la nube se asignan a los puertos en la máquina virtual individual. Todos los puertos son TCP.

|Conexión|Puerto en el servicio en la nube|Puerto en la máquina virtual|
|-|-|-|
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Connector|30400|30398|
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Forwarder|31400|31398|
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Forwarderx86|31401|31399|
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.FileUpload|32400|32398|

## <a name="see-also"></a>Vea también
- [Depuración remota](../debugger/remote-debugging.md)
