---
title: Tiempo de ejecución (vista de subprocesos) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.execution
helpviewer_keywords:
- Concurrency Visualizer, Execution Time (Threads View)
ms.assetid: 80c100f8-2502-4613-bfef-4f4f2e09cc8d
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b4306e030c2f48d87b12ba6338a847dc9e9aa892
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2019
ms.locfileid: "54766248"
---
# <a name="execution-time-threads-view"></a>Tiempo de ejecución (Vista de subprocesos)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Estos segmentos de la escala de tiempo de la vista de subprocesos representan el tiempo de ejecución, cuando el subproceso está realizando activamente una tarea en un núcleo lógico en el sistema.  
  
 Los cambios en el estado del subproceso se detectan mediante eventos de cambio de contexto de kernel. El seguimiento de eventos para Windows (ETW) captura pilas de muestras cada milisegundo. En un segmento verde muy corto, es posible que no se tome ninguna muestra. Por lo tanto, puede que algunos segmentos de ejecución cortos no muestren ninguna pila de llamadas.  
  
 Al hacer clic en un segmento de ejecución, el visualizador de simultaneidad muestra la pila de muestras más cercana a la ubicación del clic. La ubicación de esa pila de muestras se indica mediante una flecha negra, o un símbolo de intercalación, sobre la escala de tiempo y la pila de muestras aparece en la pestaña **Actual**.  
  
 Para ver un perfil de muestreo tradicional para todos los segmentos de ejecución en la vista actual, haga clic en **Ejecución** en el perfil de escala de tiempo visible.  
  
## <a name="see-also"></a>Vea también  
 [Informe del perfil de ejecución](../profiling/execution-profile-report.md)   
 [Vista de subprocesos](../profiling/threads-view-parallel-performance.md)
