---
title: 'Vista Proceso: datos de contención | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Process view
ms.assetid: 8821d98c-0771-43b2-a38b-e9039a3abd75
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 30c938088538bcecc71e3a7e37d5ae403dd476e1
ms.sourcegitcommit: 00b71889bd72b6a566586885bdb982cfe807cf54
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74778406"
---
# <a name="process-view---contention-data"></a>Vista Proceso: datos de contención
La vista Proceso muestra datos de contención de los procesos y subprocesos que se ejecutaron durante la generación de perfiles.

 Cuando haya símbolos disponibles, los procesos se enumeran por nombre. Cuando no haya símbolos disponibles, los procesos se enumeran por su dirección de memoria en formato hexadecimal. Los subprocesos se enumeran como elementos secundarios del proceso que los creó.

 En la siguiente tabla se explican los valores de las columnas de la tabla de vista Proceso.

|Columna|DESCRIPCIÓN|
|------------|-----------------|
|**Hora de inicio**|El número de milisegundos o ciclos de procesador desde el inicio de la generación de perfiles hasta el inicio del proceso o subproceso.|
|**Tiempo de bloqueo**|El tiempo total durante el cual no se pudieron ejecutar las funciones del proceso o subproceso.|
|**Porcentaje de tiempo de bloqueo**|El porcentaje de la duración del proceso o subproceso en el que no se pudieron ejecutar las funciones del proceso o subproceso.|
|**Contenciones**|El número de veces que no se pudieron ejecutar las funciones del proceso o subproceso.|
|**Porcentaje de contenciones**|El porcentaje de todas las contenciones de la generación de perfiles que son contenciones del proceso o subproceso.|
|**Hora de finalización**|El número de milisegundos o ciclos de procesador desde el inicio de la generación de perfiles hasta el final del proceso o subproceso.|
|**ID**|El identificador generado por el sistema del proceso o subproceso.|
|**Duración**|El número de milisegundos o ciclos de procesador desde el inicio del proceso o subproceso hasta el final del proceso o subproceso o el final de la generación de perfiles.|
|**ype**|El tipo de fila, ya sea un proceso o un subproceso.<br /><br /> Solo disponible en los informes de línea de comandos de **VSReport**. Para obtener más información, consulte [VSPerfReport](../profiling/vsperfreport.md).|
|**Name**|El nombre del proceso o subproceso.|
|**Id. único**|Un identificador generado por el generador de perfiles que es único para el proceso o subproceso.|

## <a name="see-also"></a>Vea también
- [Cómo: Personalizar las columnas de la vista de informes](../profiling/how-to-customize-report-view-columns.md)
- [Vista Proceso](../profiling/process-view.md)
