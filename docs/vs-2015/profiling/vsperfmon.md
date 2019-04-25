---
title: VSPerfMon | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- VSPerfMon tool
- command line, tools
- command-line tools, VSPerfMon tool
- data [Visual Studio ALM], VSPerfMon tool
- performance data, VSPerfMon tool
- performance tools, VSPerfMon tool
- profilng tools,VSPerfCmd
ms.assetid: 37052afb-7a58-441f-bb17-f1587cc57068
caps.latest.revision: 35
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4a06a6632d62f853eef33cad00ad766e0d1aab87
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2019
ms.locfileid: "54776058"
---
# <a name="vsperfmon"></a>VSPerfMon
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La herramienta VSPerfMon, que normalmente suele iniciar VSPerfCmd.exe, puede utilizarse para recopilar datos de rendimiento de una aplicación. VSPerfMon muestra información adicional sobre el proceso de adjuntar o separar que no está disponible mediante la herramienta VSPerfCmd. Para ver esta información, inicie VSPerfMon en una ventana independiente. Para invocar VSPerfMon, utilice la siguiente sintaxis:  
  
```  
VSPerfMon [/U] </TRACE [/COUNTER:cfg] | /SAMPLE | /COVERAGE> /CROSSSESSION /OUTPUT <file name> [/WINCOUNTER:cfg] [/USER [DOMAIN\]username]  
```  
  
 En la siguiente tabla se describen las opciones de la herramienta VSPerfMon:  
  
|Opciones|Descripción|  
|-------------|-----------------|  
|**U**|Se escribe la salida de la consola redirigida como Unicode.  Esta debe ser la primera opción especificada.|  
|**OUTPUT:** `<` *file name* `>`|Redirige la salida al nombre de archivo especificado.|  
|**TRACE**|Inicia el monitor de rendimiento para la generación de perfiles instrumentada.|  
|**SAMPLE**|Inicia el monitor de rendimiento para la generación de perfiles de muestreo.|  
|**COVERAGE**|Inicia el monitor de rendimiento para la recolección de cobertura de código.|  
|**CONCURRENCY**|Inicia al monitor de rendimiento para la generación de perfiles de contención de recursos.|  
|**USER:** `[` *domain* `\]` *username*|Permite el acceso de cliente al monitor de rendimiento desde la cuenta especificada.|  
|**CROSSSESSION**|Permite la generación de perfiles entre sesiones.|  
|**COUNTER** `:cfg`|Cuando se utiliza el método de generación de perfiles instrumentación (TRACE), especifica un contador de CPU que se recopila en cada punto de instrumentación. Puede recopilar datos de varios contadores especificando varias opciones Counter.<br /><br /> Utilice la siguiente sintaxis para especificar los datos del contador (*cfg*):<br /><br /> **CounterName** [**,Reload**[,**FriendlyName**]]<br /><br /> -   **CounterName** es el nombre de un contador devuelto por el comando /QueryCounters de VSPerfCmd.<br />-   **Reload** es el intervalo de muestreo de eventos de contador. No utilice *Reload* con el método de instrumentación.<br />-   Cuando se especifica, **FriendlyName** reemplaza **CounterName** en los nombres de columna del informe de herramientas de generación de perfiles.|  
|**WINCOUNTER** `:path`|Especifica un contador de rendimiento de Windows que se incluirá con datos de marca. `path` es una cadena de contador de rendimiento de Windows en formato de ruta de acceso de contador PDH. Por ejemplo:<br /><br /> \Processor(0)\\% Processor Time<br /><br /> \System\Context Switches/sec|  
|**AUTOMARK** `:n`|Especifica el intervalo de tiempo (en milisegundos) entre marcas automáticas cuando se usa /WINCOUNTER. Redondeado a los 500 ms más cercanos.<br /><br /> Use 0 para deshabilitar las marcas automáticas. (predeterminado = 500 ms si no se especifica)|  
  
## <a name="see-also"></a>Vea también  
 [VSInstr](../profiling/vsinstr.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [VSPerfReport](../profiling/vsperfreport.md)   
 [Vistas de informes de rendimiento](../profiling/performance-report-views.md)
