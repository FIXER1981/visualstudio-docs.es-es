---
title: 'Vista Funciones: datos de muestreo | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- sampling profiling method,Functions View
- Functions view
ms.assetid: 029d5ebb-e551-46b0-b64e-2c553d9dbb8e
caps.latest.revision: 17
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 68280c4da20ce063b93b7347cc2857d4a83b9a18
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2019
ms.locfileid: "54769167"
---
# <a name="functions-view---sampling-data"></a>Vista Funciones: datos de muestreo
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La vista de informe de funciones para el método de perfiles de muestreo enumera las funciones que se muestrearon durante la ejecución de generación de perfiles.  
  
> [!NOTE]
>  Las características de seguridad mejoradas en Windows 8 y Windows Server 2012 requirieron cambios significativos en la forma en que el generador de perfiles de Visual Studio recopila datos en estas plataformas. Las aplicaciones de la Tienda Windows también requieren nuevas técnicas de recolección. Consulte [Herramientas de rendimiento en aplicaciones de Windows 8 y Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
|Columna|Descripción|  
|------------|-----------------|  
|**Identificador del proceso**|Identificador de proceso (PID) de la ejecución de generación de perfiles.|  
|**Nombre de proceso**|Nombre del proceso.|  
|**Nombre del módulo**|Nombre del módulo que contiene la función.|  
|**Ruta de acceso del módulo**|Ruta de acceso del módulo que contiene la función.|  
|**Archivo de código fuente**|Archivo de origen que contiene la definición de esta función.|  
|**Nombre de la función**|El nombre completo de la función.|  
|**Número de línea de la función**|Número de línea del inicio de esta función en el archivo de origen.|  
|**Dirección de la función**|Dirección de la función.|  
|**Muestras inclusivas**|El número total de muestras recopiladas cuando se estaba ejecutando esta función; es decir, el número de muestras recopiladas cuando esta función estaba en la pila de llamadas. El número incluye las muestras recopiladas cuando se ejecutaban funciones a las que llamó esta función.|  
|**Porcentaje de muestras inclusivas**|El porcentaje de todas las muestras de la ejecución de generación de perfiles que fueron muestras inclusivas de esta función.|  
|**Muestras exclusivas**|El número total de muestras recopiladas cuando se estaba ejecutando código en el cuerpo de esta función; es decir, cuando esta función estaba en la parte superior de la pila de llamadas. Las muestras recopiladas en funciones a las que llamó esta función no se incluyen.|  
|**Porcentaje de muestras exclusivas**|El porcentaje de todas las muestras de la ejecución de generación de perfiles que fueron muestras exclusivas de esta función.|  
  
## <a name="see-also"></a>Vea también  
 [Cómo: Personalizar las columnas de la vista de informes](../profiling/how-to-customize-report-view-columns.md)   
 [Vista Funciones: instrumentación](../profiling/functions-view-dotnet-memory-instrumentation-data.md)   
 [Vista Funciones: muestreo](../profiling/functions-view-dotnet-memory-sampling-data.md)   
 [Vista Funciones](../profiling/functions-view-instrumentation-data.md)
