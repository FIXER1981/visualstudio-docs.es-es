---
title: 'CA1505: Evitar código que no se puede mantener'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AvoidUnmaintainableCode
- CA1505
helpviewer_keywords:
- AvoidUnmaintainableCode
- CA1505
ms.assetid: 8292b268-5929-4221-b699-f9c414bcec5d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 740ef26af6f1f84d23ef27de5176df1b3de98b34
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59232501"
---
# <a name="ca1505-avoid-unmaintainable-code"></a>CA1505: Evitar código que no se puede mantener

|||
|-|-|
|TypeName|AvoidUnmantainableCode|
|Identificador de comprobación|CA1505|
|Categoría|Microsoft.Maintainability|
|Cambio problemático|Poco problemático|

## <a name="cause"></a>Motivo

Un tipo o método tiene un valor del índice de mantenimiento bajo.

## <a name="rule-description"></a>Descripción de la regla

El índice de mantenimiento se calcula mediante el uso de las siguientes métricas: líneas de código, el volumen del programa y complejidad ciclomática. Volumen del programa es una medida de la dificultad de comprensión de un tipo o método que se basa en el número de operadores y operandos en el código. Complejidad ciclomática es una medida de la complejidad estructural del tipo o método. Puede aprender más acerca de las métricas de código en [medir la complejidad y el mantenimiento del código administrado](../code-quality/code-metrics-values.md).

Un índice de mantenimiento bajo indica que un tipo o método resulta probablemente difícil de mantener y sería un buen candidato para volver a diseñar.

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones

Para corregir esta infracción, vuelva a diseñar el tipo o método e intente dividir más corta y tipos o métodos.

## <a name="when-to-suppress-warnings"></a>Cuándo Suprimir advertencias

Puede suprimir esta advertencia cuando el tipo o método no se puede dividir o se considera fácil de mantener a pesar de su gran tamaño.

## <a name="see-also"></a>Vea también

- [Advertencias de mantenimiento](../code-quality/maintainability-warnings.md)
- [Medir la complejidad y el mantenimiento del código administrado](../code-quality/code-metrics-values.md)