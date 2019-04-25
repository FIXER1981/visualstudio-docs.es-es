---
title: 'Vista Resumen: datos de muestreo | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- sampling profiling method, Summary view
- Summary view
ms.assetid: 79056873-2985-40be-9112-cdbc26a65156
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9b98dc1baa94b9df4039718695ebe26ebf59da46
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56614459"
---
# <a name="summary-view---sampling-data"></a>Vista Resumen: datos de muestreo
La vista Resumen muestra información acerca de las funciones más exigentes en una generación de perfiles. Para obtener más información, incluyendo una descripción de los vínculos de notificación y las listas de informes, consulte [Vista Resumen](../profiling/summary-view.md).

> [!NOTE]
>  Las características de seguridad mejoradas en Windows 8 y Windows Server 2012 requirieron cambios significativos en la forma en que el generador de perfiles de Visual Studio recopila datos en estas plataformas. Las aplicaciones para UWP también requieren nuevas técnicas de recopilación. Consulte [Herramientas de rendimiento en aplicaciones de Windows 8 y Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

## <a name="timeline-graph"></a>Gráfico de escala de tiempo
 El gráfico de escala de tiempo en la vista Resumen muestra el porcentaje de utilización del procesador (CPU) de la aplicación de la que se generan perfiles durante el tiempo que se generaron perfiles. Puede usar el gráfico de escala de tiempo para filtrar la vista en un intervalo de tiempo seleccionado. Para obtener más información, vea [Cómo: Filtrar vistas de informe desde la escala de tiempo de resumen](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).

## <a name="hot-path"></a>Ruta de acceso activa
 La **Ruta de acceso activa** muestra la ruta de acceso de ejecución en la que se recopilaron más muestras. Puede hacer clic en una función para mostrar la vista Detalles de la misma. Para mostrar otras vistas para la función haga clic con el botón derecho en ella y después haga clic en una vista de la lista.

 La **Ruta de acceso activa** incluye los siguientes datos para cada función:

|Columna|Descripción|
|------------|-----------------|
|**Name**|Nombre de la función.|
|**Porcentaje de muestras inclusivas**|El porcentaje de todas las muestras que se produjeron cuando se estaba ejecutando esta función o una función a la que llamó.|
|**Porcentaje de muestras exclusivas**|El porcentaje de todas las muestras que se produjeron cuando estaba ejecutando código la función en el cuerpo de la función. No se incluyen muestras recopiladas en las funciones a las que llamó esta función.|

## <a name="functions-doing-most-individual-work"></a>Funciones que realizan la mayor parte de trabajo individual
 La lista **Funciones que realizan la mayor parte de trabajo individual** muestra las funciones que tienen el mayor número de muestras exclusivas en la generación de perfiles. Una muestra exclusiva se asigna a una función si la función está ejecutando su propio código cuando se recopila la muestra. Una muestra exclusiva no se asigna a una función si la función está llamando a otra cuando se recopila la muestra. Un gran número de muestras exclusivas indica que se dedicó un tiempo considerable a la propia función.

 Puede hacer clic en una función para mostrar la vista Detalles de la misma. Para mostrar otras vistas para la función haga clic con el botón derecho en ella y después haga clic en una vista de la lista.

 **Funciones que realizan la mayor parte de trabajo individual** incluye los siguientes datos para cada función:

|Columna|Descripción|
|------------|-----------------|
|**Name**|Nombre de la función.|
|**Porcentaje de muestras exclusivas**|El porcentaje de todas las muestras que se recopilaron durante la generación de perfiles mientras la función ejecutaba código en el cuerpo de la función. El porcentaje excluye las muestras recopiladas cuando se estaban ejecutando las funciones a las que llamó esta función.|

## <a name="see-also"></a>Vea también
- [Vista de resumen: datos de memoria de .NET](../profiling/summary-view-dotnet-memory-data.md)
- [Vista Resumen: datos de instrumentación](../profiling/summary-view-instrumentation-data.md)