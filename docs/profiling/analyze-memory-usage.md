---
title: Analizar el uso de memoria
ms.custom: seodec18
ms.date: 10/12/2020
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0262081489ec6e037a006649c3041baf02b32d58
ms.sourcegitcommit: 172aaf05596a9d8ded298b7b104569c1cce6160e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "92007215"
---
# <a name="analyze-memory-usage"></a>Analizar el uso de memoria

Para detectar fugas y usos ineficaces de memoria, puede usar utilidades como la herramienta de diagnóstico Uso de memoria integrada en el depurador o las herramientas del Generador de perfiles de rendimiento como Asignación de objetos .NET y Uso de memoria final.

La herramienta Uso de memoria permite tomar una o más *instantáneas* del montón de memoria nativo y administrado. Puede recopilar instantáneas de aplicaciones .NET, ASP.NET, C++ o de modo mixto (.NET y nativas). La herramienta **Uso de memoria** puede ejecutarse en un proyecto abierto de Visual Studio, en una aplicación instalada de Microsoft Store o asociada a una aplicación o un proceso en ejecución. Puede ejecutar la herramienta **Uso de memoria** con o sin depuración. Para obtener más información, vea [Ejecutar herramientas de generación de perfiles con o sin el depurador](../profiling/running-profiling-tools-with-or-without-the-debugger.md). En el depurador, puede activar y desactivar la generación de perfiles de memoria y ver un desglose por objeto de uso de memoria. Puede ver los resultados de uso de memoria mientras la ejecución está en pausa, por ejemplo, en un punto de interrupción.

Los desarrolladores de .NET pueden elegir entre la herramienta [Uso de memoria](../profiling/memory-usage.md) y la [herramienta de asignación de objetos .NET](../profiling/dotnet-alloc-tool.md).
- La **herramienta de asignación de objetos .NET** ayuda a identificar patrones de asignación y anomalías en el código de .NET, además de problemas habituales en la recolección de elementos no utilizados. Esta herramienta solo se ejecuta a modo de análisis post mortem. Puede ejecutar esta herramienta en máquinas locales o remotas.
- La herramienta **Uso de memoria** es útil para identificar fugas de memoria, que no suelen ser habituales en aplicaciones .NET. Si necesita usar características del depurador mientras comprueba la memoria, como ejecutar paso a paso el código, se recomienda la herramienta [Uso de memoria integrada en el depurador](../profiling/beginners-guide-to-performance-profiling.md).

Las herramientas de generación de perfiles se pueden usar sin el depurador en Windows 7 y versiones posteriores. Para ejecutar las herramientas de generación de perfiles con el depurador se requiere Windows 8 y versiones posteriores (ventana **Herramientas de diagnóstico** ).

## <a name="blogs-and-videos"></a>Blogs y vídeos

[Analyze CPU and Memory While Debugging](https://devblogs.microsoft.com/visualstudio/analyze-cpu-memory-while-debugging/) (Análisis de la CPU y la memoria durante la depuración)

[Blog de Visual C++: Generación de perfiles de memoria en Visual C++ 2015](https://devblogs.microsoft.com/cppblog/memory-profiling-in-visual-c-2015/)

## <a name="see-also"></a>Vea también

- [Análisis del uso de memoria sin el depurador](../profiling/memory-usage-without-debugging2.md)
- [Generación de perfiles en Visual Studio](../profiling/index.yml)
- [Primer vistazo a la generación de perfiles](../profiling/profiling-feature-tour.md)
