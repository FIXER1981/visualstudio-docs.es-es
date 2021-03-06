---
title: Usar reglas de rendimiento para analizar datos | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 1deed23e-b31b-4714-982f-08ceebfc3096
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 3ea0f43b63eb8ec51ad7e8240844a804259374a8
ms.sourcegitcommit: c025a5e2013c4955ca685092b13e887ce64aaf64
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2020
ms.locfileid: "91659347"
---
# <a name="use-performance-rules-to-analyze-data"></a>Usar reglas de rendimiento para el análisis de datos
Las advertencias de rendimiento de las herramientas de generación de perfiles de [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] indican problemas en una aplicación para la que se han generado perfiles que pueden ralentizar la ejecución de programas. Las advertencias también pueden indicar que puede ser necesario cambiar los métodos de recolección para recopilar datos más útiles. Las advertencias de rendimiento se generan automáticamente en una sesión de generación de perfiles. Las advertencias aparecen en la ventana **Lista de errores** cuando un archivo de datos de generación de perfiles se abre en Visual Studio. En la ventana **Lista de errores**, puede buscar el código fuente del problema y puede mostrar información detallada sobre el error, como información sobre la forma de resolver el problema. También puede deshabilitar advertencias en las que no está interesado.

> [!NOTE]
> Las advertencias de rendimiento del generador de perfiles son generadas por el análisis dinámico de ejecución de programas y son independientes de las advertencias del análisis de código. El análisis de código también puede generar advertencias de rendimiento para código administrado en función del análisis estático del código fuente. Para obtener más información, vea [Analizar la calidad del código administrado](../code-quality/code-analysis-for-managed-code-overview.md) y [Advertencias de rendimiento](/dotnet/fundamentals/code-analysis/quality-rules/performance-warnings).

## <a name="in-this-section"></a>En esta sección
- [Visualización de advertencias de rendimiento](../profiling/how-to-view-performance-warnings.md)

 Proporciona información sobre cómo abrir la ventana **Lista de errores** para ver las advertencias de rendimiento del generador de perfiles.

- [Configuración de las reglas de rendimiento](../profiling/how-to-configure-performance-rules.md)

 Proporciona información sobre cómo activar o desactivar las advertencias de rendimiento individuales.

- [Referencia de reglas de rendimiento](../profiling/performance-rules-reference.md)

 Proporciona información detallada sobre las advertencias de rendimiento del generador de perfiles.
