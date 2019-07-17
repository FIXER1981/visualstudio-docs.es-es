---
title: 'CA1601: No utilizar temporizadores que impidan los cambios de estado de energía | Documentos de Microsoft'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
helpviewer_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
ms.assetid: b8028c92-0696-4c54-9773-0028f29bda9a
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 228c95a8f0c3e1b9b1643e529e78f52f1e059bc5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "68189250"
---
# <a name="ca1601-do-not-use-timers-that-prevent-power-state-changes"></a>CA1601: No utilizar temporizadores que impidan los cambios de estado de energía
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotUseTimersThatPreventPowerStateChanges|
|Identificador de comprobación|CA1601|
|Categoría|Microsoft.Mobility|
|Cambio problemático|Problemático|

## <a name="cause"></a>Causa
 Un temporizador tiene un intervalo establecido que se produzca más de una vez por segundo.

## <a name="rule-description"></a>Descripción de la regla
 No sondear más de una vez por segundo o utilizar temporizadores que se producen con más frecuencia que una vez por segundo. Una actividad periódica más frecuente hará que la CPU no esté disponible, e interferirá con los temporizadores de inactividad para ahorro de energía, que apagan el monitor y el disco duro.

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones
 Establecer los intervalos de temporizador que se produzcan menos de una vez por segundo.

## <a name="when-to-suppress-warnings"></a>Cuándo suprimir advertencias
 Esta regla se debe suprimir sólo si desencadenar el temporizador de más de una vez por segundo es necesario y las consideraciones de movilidad se pueden omitir.
