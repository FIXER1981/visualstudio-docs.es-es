---
title: Generación de perfiles de aplicaciones independientes en la línea de comandos | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profillng tools,stand-alone applications
- profling stand-alone applications
ms.assetid: a47f2bf2-186d-4120-bb79-34e2f3a1ee42
caps.latest.revision: 21
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3f4b2b78f7187b7a49b78312a1105a2af884fda3
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54752193"
---
# <a name="command-line-profiling-of-stand-alone-applications"></a>Generación de perfiles de aplicaciones independientes en la línea de comandos
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

En esta sección se describen los procedimientos y las opciones para recopilar datos de rendimiento de aplicaciones independientes (cliente) mediante las herramientas de generación de perfiles [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] desde la línea de comandos.  
  
## <a name="common-tasks"></a>Tareas comunes  
  
|Tarea|Contenido relacionado|  
|----------|---------------------|  
|**Recopilar estadísticas de aplicación**: Use el método de muestreo para recopilar estadísticas de rendimiento. Los datos de muestreo son útiles para analizar problemas de uso de CPU y para entender las características de rendimiento generales de una aplicación.|-   [Recopilar estadísticas de aplicación mediante muestreo](../profiling/collecting-application-statistics-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Recopilar datos detallados de tiempo**: Use el método de instrumentación para recopilar información de tiempo detallada. Los datos de instrumentación son útiles para analizar problemas de E/S y para el análisis detallado de escenarios de aplicación.|-   [Recopilar datos de control de tiempo detallados utilizando la instrumentación](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application-by-using-the-profiler-command-line.md)|  
|**Recopilar datos de memoria de .NET**: Use el muestreo o la instrumentación para recopilar datos de asignación de memoria de .NET que muestran el tamaño y el número de objetos asignados. También puede recopilar datos de duración de objetos que muestran el tamaño y el número de los objetos reclamados en cada generación de recolección de elementos no utilizados.|-   [Recopilar datos de memoria de .NET Framework](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Recopilar datos de simultaneidad**: Use el método de simultaneidad para recopilar datos de contención de recursos y de actividad de subprocesos que muestran el uso de CPU, la contención de subprocesos, la migración de subprocesos, los retrasos de sincronización, las áreas de E/S superpuesta y otros eventos del sistema.|-   [Recopilar datos de simultaneidad](../profiling/collecting-concurrency-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Agregar datos de interacción de capas:** Puede agregar datos de rendimiento de las llamadas de ADO.NET sincrónicas que la aplicación ha realizado a una base de datos de Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. Agregar datos de interacción de capas a una ejecución de generación de perfiles requiere procedimientos concretos con las Herramientas de generación de perfiles de la línea de comandos.|-   [Recopilar datos de interacción de capas](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**Pruébelo:** Use procedimientos detallados para generar perfiles de una aplicación cliente de ejemplo mediante el método de muestreo o instrumentación.|-   [Tutorial: Generación de perfiles de línea de comandos mediante muestreo](../profiling/walkthrough-command-line-profiling-using-sampling.md)<br />-   [Tutorial: Generación de perfiles mediante instrumentación desde la línea de comandos](../profiling/walkthrough-command-line-profiling-using-instrumentation.md)|  
  
## <a name="related-tasks"></a>Tareas relacionadas  
  
|Tarea|Contenido relacionado|  
|----------|---------------------|  
|**Generar perfiles de aplicaciones ASP.NET**|-   [Generar perfiles de aplicaciones web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)|  
|**Generar perfiles para servicios**|-   [Generar perfiles para servicios](../profiling/command-line-profiling-of-services.md)|
