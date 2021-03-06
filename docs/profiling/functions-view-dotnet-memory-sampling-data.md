---
title: 'Vista Funciones: datos de muestreo de memoria de .NET | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Functions view
ms.assetid: 5d9c6302-2ffd-430e-9535-13ce795f9f7c
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- dotnet
ms.openlocfilehash: cce13da0c2dfee61d70da8bc288d1f0ff4690deb
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "74780044"
---
# <a name="functions-view---net-memory-sampling-data"></a>Vista Funciones: datos de muestreo de memoria de .NET
La vista Funciones de los datos de generación de perfiles de asignación de memoria de .NET recopilados mediante el método de muestreo enumera las funciones que han asignado memoria durante la ejecución de generación de perfiles e informa del tamaño y número de asignaciones.

|Columna|Description|
|------------|-----------------|
|**Identificador del proceso**|Identificador de proceso (PID) de la ejecución de generación de perfiles.|
|**Nombre del proceso**|Nombre del proceso.|
|**Nombre del módulo**|Nombre del módulo que contiene la función.|
|**Ruta de acceso del módulo**|Ruta de acceso del módulo que contiene la función.|
|**Archivo de origen**|Archivo de origen que contiene la definición de esta función.|
|**Nombre de la función**|El nombre completo de la función.|
|**Número de línea de la función**|Número de línea del inicio de esta función en el archivo de origen.|
|**Dirección de función**|Dirección de la función.|
|**Asignaciones inclusivas**|Número total de objetos asignados en esta función y sus funciones secundarias.|
|**Porcentaje de asignaciones inclusivas**|Porcentaje de todos los objetos que se han asignado durante la ejecución de la generación de perfiles que eran asignaciones inclusivas de esta función.|
|**Asignaciones exclusivas**|Número de objetos creados cuando la función se estaba ejecutando directamente en la parte superior de la pila de llamadas. Este número no incluye los objetos creados en funciones secundarias.|
|**Porcentaje de asignaciones exclusivas**|Porcentaje de todos los objetos que se han asignado durante la ejecución de la generación de perfiles que eran asignaciones exclusivas de esta función.|
|**Bytes inclusivos**|Número de bytes de memoria asignados por esta función y sus funciones secundarias.|
|**Porcentaje de bytes inclusivos**|Porcentaje de todos los bytes de memoria que se han asignado durante la ejecución de la generación de perfiles que eran bytes inclusivos de esta función.|
|**Bytes exclusivos**|Número de bytes de memoria asignados por esta función, pero no por sus funciones secundarias.|
|**Porcentaje de bytes exclusivos**|Porcentaje de todos los bytes de memoria que se han asignado durante la ejecución de la generación de perfiles que eran bytes exclusivos de esta función.|

## <a name="see-also"></a>Vea también
- [Vista Funciones: instrumentación](../profiling/functions-view-dotnet-memory-instrumentation-data.md)
- [Vista Funciones](../profiling/functions-view-sampling-data.md)
- [Vista Funciones](../profiling/functions-view-instrumentation-data.md)
