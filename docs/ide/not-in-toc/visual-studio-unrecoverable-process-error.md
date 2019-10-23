---
title: Un proceso ha detectado un error irrecuperable
ms.date: 06/22/2018
ms.topic: troubleshooting
helpviewer_keywords:
- unrecoverable error
- error, process
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6fae832cf62b2cfc6302289352bc5a2f2afb9f13
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2019
ms.locfileid: "72667053"
---
# <a name="visual-studio-unrecoverable-process-error"></a>Error irrecuperable del proceso de Visual Studio

Visual Studio usa varios procesos fuera de proceso para ejecutar las tareas en segundo plano necesarias, como Live Unit Testing, analizadores de código, etc. Estos procesos se ejecutan fuera de proceso para proporcionar ventajas de rendimiento a Visual Studio, como permitirle responder con mayor rapidez cuando se ejecutan trabajos de larga ejecución que consumen muchos recursos. Además, dado que Visual Studio es un proceso de 32 bits, la ejecución de procesos fuera de proceso proporciona a los trabajos que consumen mucha memoria un mayor espacio de memoria en el que operar.

Si el proceso *ServiceHub.RoslynCodeAnalysisService.exe* o *ServiceHub.RoslynCodeAnalysisService32.exe* finalizan por algún motivo, aparece una barra de información emergente con el mensaje siguiente:

**"Unfortunately, a process used by Visual Studio has encountered an unrecoverable error. We recommend saving your work, and then closing and restarting Visual Studio." (Lamentablemente, un proceso usado por Visual Studio ha detectado un error irrecuperable. Le recomendamos que guarde su trabajo y, después, cierre y reinicie Visual Studio).**

Si ve este mensaje, debe guardar el trabajo y, después, cerrar y reiniciar Visual Studio.

## <a name="list-of-processes"></a>Lista de procesos

A continuación encontrará una lista de procesos fuera de proceso usados por Visual Studio. Esta lista incluye los procesos que se ejecutan en escenarios o flujos de trabajo específicos y que, en la mayoría de casos, no se ejecutan todos al mismo tiempo.

- Microsoft.Alm.Shared.Remoting.RemoteContainer.dll
- Microsoft.CodeAnalysis.LiveUnitTesting.EntryPoint
- PerfWatson2.exe
- ServiceHub.Host.Node.x86.exe
- ServiceHub.IdentityHost.exe
- ServiceHub.VSDetouredHost.exe
- ServiceHub.SettingsHost.exe
- ServiceHub.Host.CLR.x86.exe
- ServiceHub.RoslynCodeAnalysisService32.exe
- ServiceHub.RoslynCodeAnalysisService.exe
- WindowsAzureGuestAgent.exe
- WindowsAzureTelemetryService.exe
- WaAppAgent.exe

Si alguno de estos procesos finaliza inesperadamente, alguna funcionalidad de Visual Studio deja de funcionar. En algunos procesos, la pérdida de funcionalidad puede ser insignificante. En otros casos, afecta a la estabilidad de Visual Studio y se muestra un mensaje de error.