---
title: Habilitar o deshabilitar el análisis de código
ms.date: 10/25/2018
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 4878c25021d87e91f6a575d11a876d7aac2455d5
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55918135"
---
# <a name="how-to-enable-and-disable-automatic-code-analysis-for-managed-code"></a>Filtrar Habilitar y deshabilitar el análisis de código automático para código administrado

Puede configurar el análisis de código (estático) para ejecutar después de cada compilación de un proyecto de código administrado. Puede establecer propiedades de análisis para cada configuración de compilación de código diferente, por ejemplo, debug y release.

En este artículo se aplica a análisis de código estático sólo a y el análisis de código en vivo no con [analizadores de código Roslyn](roslyn-analyzers-overview.md).

## <a name="to-enable-or-disable-automatic-code-analysis"></a>Para habilitar o deshabilitar el análisis de código automático

1. En **el Explorador de soluciones**, haga clic en el proyecto y, a continuación, elija **propiedades**.

1. En el cuadro de diálogo Propiedades del proyecto, elija el **análisis de código** ficha.

   > [!TIP]
   > Los tipos de proyecto más reciente como las aplicaciones de .NET Core y .NET Standard no tienen un **análisis de código** ficha. Análisis de código estático no está disponible para estos tipos de proyecto, pero todavía puede obtener análisis de código en vivo con [analizadores de código Roslyn](roslyn-analyzers-overview.md). Para suprimir las advertencias de los analizadores de Roslyn de código, consulte la nota al final de este artículo.

1. Especifique el tipo de compilación en **configuración** y la plataforma de destino en **plataforma**.

1. Para habilitar o deshabilitar el análisis de código automático, active o desactive el **Habilitar análisis de código al compilar** casilla de verificación.

> [!NOTE]
> El **Habilitar análisis de código al compilar** casilla de verificación sólo afecta a los análisis de código estático. No se ve afectada [analizadores de código Roslyn](roslyn-analyzers-overview.md), que siempre se ejecutan en la compilación si se instaló como un paquete de NuGet. Si desea borrar errores del analizador desde la **lista de errores**, puede suprimir todas las infracciones actuales eligiendo **analizar** > **ejecutar análisis de código y suprimir activo Problemas** en la barra de menús. Para obtener más información, consulte [suprimir infracciones](use-roslyn-analyzers.md#suppress-violations).
