---
title: 'CA1900: los campos de tipo de valor deben ser portátiles | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1900
- ValueTypeFieldsShouldBePortable
helpviewer_keywords:
- ValueTypeFieldsShouldBePortable
- CA1900
ms.assetid: 1787d371-389f-4d39-b305-12b53bc0dfb9
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 2ece4788a277bfc4d16568d4014f9eae2ed4de33
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "85545280"
---
# <a name="ca1900-value-type-fields-should-be-portable"></a>CA1900: Los campos de tipo de valor deben ser portátiles
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Para obtener la documentación más reciente sobre Visual Studio, vea [CA1900: los campos de tipo de valor deben ser portátiles](/visualstudio/code-quality/ca1900-value-type-fields-should-be-portable).

|Elemento|Value|
|-|-|
|TypeName|ValueTypeFieldsShouldBePortable|
|Identificador de comprobación|CA1900|
|Category|Microsoft. portabilidad|
|Cambio problemático|Interrumpir: Si el campo puede verse fuera del ensamblado.<br /><br /> No problemático: Si el campo no es visible fuera del ensamblado.|

## <a name="cause"></a>Causa
 Esta regla comprueba que las estructuras que se declaran con diseño explícito se alinearán correctamente cuando se calculen las referencias a código no administrado en sistemas operativos de 64 bits. IA-64 no permite el acceso a memoria no alineada y el proceso se bloqueará si esta infracción no es fija.

## <a name="rule-description"></a>Descripción de la regla
 Las estructuras que tienen un diseño explícito que contiene campos desalineados causan bloqueos en los sistemas operativos de 64 bits.

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones
 Todos los campos de menos de 8 bytes deben tener desplazamientos que sean un múltiplo de su tamaño, y los campos de 8 bytes o más deben tener desplazamientos que sean un múltiplo de 8. Otra solución consiste en usar `LayoutKind.Sequential` en lugar de `LayoutKind.Explicit` , si es razonable.

## <a name="when-to-suppress-warnings"></a>Cuándo suprimir advertencias
 Esta advertencia solo se debe suprimir si se produce un error.
