---
title: Vista Proceso | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.process
helpviewer_keywords:
- performance tools reports, process view
- Process view
- performance tools, process view
- Profiling Tools,process view
- Profiling Tools,process report
ms.assetid: 6d4e2a5d-9f17-4ece-a6f1-75836e1fc382
caps.latest.revision: 17
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 0436401c458a7d6771a2785028a8b5fe0ef57546
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68180220"
---
# <a name="process-view"></a>Vista Proceso
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La vista Proceso muestra los datos de generación de perfiles de los procesos y subprocesos que se ejecutaron durante la generación de perfiles.  
  
 Los procesos se ordenan por nombre. Los subprocesos se enumeran como nodos secundarios del proceso que los creó. Los subprocesos son denominados por la función que inició el subproceso o por la etiqueta **[ntdll.dll]** si no hay símbolos disponibles.  
  
 Para agregar o quitar columnas, haga clic en la vista y, a continuación, seleccione **Agregar o quitar columnas**. Además, puede ordenar los datos haciendo clic en el nombre de una columna. Para obtener más información, vea [Cómo: personalizar las columnas de la vista de informe](../profiling/how-to-customize-report-view-columns.md).  
  
 Las columnas de la vista Proceso son las mismas para los datos generados mediante los métodos de instrumentación y muestreo y para los datos que incluyen los datos de memoria de .NET. En la siguiente tabla se describen estos valores de columna.  
  
|Columna|Description|  
|------------|-----------------|  
|**Id. único**|Un identificador generado por el generador de perfiles que es único para el proceso o subproceso.|  
|**ID**|El identificador generado por el sistema del proceso o subproceso.|  
|**Name**|El nombre del proceso o subproceso.|  
|**Hora de inicio**|El número de milisegundos o ciclos de procesador desde el inicio de la generación de perfiles hasta el inicio del proceso o subproceso.|  
|**Hora de finalización**|El número de milisegundos o ciclos de procesador desde el inicio de la generación de perfiles hasta el final del proceso o subproceso.|  
  
## <a name="see-also"></a>Consulte también  
 [Vistas de datos del método de muestreo](../profiling/profiler-sampling-method-data-views.md)   
 [Vistas de datos del método de instrumentación](../profiling/instrumentation-method-data-views.md)   
 [Vistas de datos de memoria de .NET](../profiling/dotnet-memory-data-views.md)
