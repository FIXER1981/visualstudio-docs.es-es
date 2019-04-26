---
title: Analizar el uso de memoria
ms.custom: seodec18
ms.date: 01/02/2018
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2e8f54b63847fca87eacc7dd19eccba6d285764a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62777351"
---
# <a name="analyze-memory-usage"></a>Analizar el uso de memoria
Utilice la herramienta de diagnóstico **Uso de memoria** con depurador integrado para buscar usos ineficaces y fugas de memoria. La herramienta Uso de memoria permite tomar una o más *instantáneas* del montón de memoria nativo y administrado. Puede recopilar instantáneas de aplicaciones .NET, ASP.NET, nativas o de modo mixto (.NET y nativas).

- Puede analizar una sola instantánea para entender el impacto relativo de los tipos de objeto en el uso de la memoria y buscar código en la aplicación que use la memoria de forma ineficaz.

- También puede comparar (diff) dos instantáneas de una aplicación para buscar las áreas del código que generen un aumento del uso de la memoria con el tiempo.

Para obtener instrucciones detalladas, vea el tutorial [Análisis del uso de memoria](../profiling/memory-usage.md).  Actualmente, para medir el uso de memoria de una aplicación .NET Core, debe usar la herramienta con el depurador adjunto. Para otras aplicaciones administradas y nativas, puede usar la herramienta ya sea con o sin el depurador adjunto.

Las herramientas de generación de perfiles se pueden usar sin el depurador en Windows 7 y versiones posteriores. Para ejecutar las herramientas de generación de perfiles con el depurador se requiere Windows 8 y versiones posteriores (ventana **Herramientas de diagnóstico**).

## <a name="blogs-and-videos"></a>Blogs y vídeos

[Analyze CPU and Memory While Debugging](https://devblogs.microsoft.com/visualstudio/analyze-cpu-memory-while-debugging/) (Análisis de la CPU y la memoria durante la depuración)

[Blog de Visual C++: Generación de perfiles de memoria en Visual C++ 2015](https://devblogs.microsoft.com/cppblog/memory-profiling-in-visual-c-2015/)

## <a name="see-also"></a>Vea también

- [Generación de perfiles en Visual Studio](../profiling/index.md)
- [Primer vistazo a la generación de perfiles](../profiling/profiling-feature-tour.md)