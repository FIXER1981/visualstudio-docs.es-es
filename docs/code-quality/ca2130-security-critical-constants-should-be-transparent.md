---
title: 'CA2130: Las constantes críticas para la seguridad deben ser transparentes'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2130
ms.assetid: 344c7f7b-9130-4675-ae7f-9fa260cc9789
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cbe1f5c58b957cf3ed226af7c7b879c7a6dcfc0a
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55970067"
---
# <a name="ca2130-security-critical-constants-should-be-transparent"></a>CA2130: Las constantes críticas para la seguridad deben ser transparentes

|||
|-|-|
|TypeName|ConstantsShouldBeTransparent|
|Identificador de comprobación|CA2130|
|Categoría|Microsoft.Security|
|Cambio problemático|Problemático|

## <a name="cause"></a>Motivo
 Un campo constante o un miembro de enumeración se marca con el <xref:System.Security.SecurityCriticalAttribute>.

## <a name="rule-description"></a>Descripción de la regla
 El cumplimiento de la transparencia no se exige para los valores constantes porque los compiladores alinean los valores constantes para que no se requiera ninguna búsqueda en tiempo de ejecución. Los campos constantes deberían ser transparentes en seguridad de modo que los revisores del código no supongan que el código transparente no puede tener acceso a la constante.

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones
 Para corregir una infracción de esta regla, quite el atributo SecurityCritical del campo o valor.

## <a name="when-to-suppress-warnings"></a>Cuándo Suprimir advertencias
 No suprima las advertencias de esta regla.

## <a name="example"></a>Ejemplo
 En los ejemplos siguientes, el valor de enumeración `EnumWithCriticalValues.CriticalEnumValue` y la constante `CriticalConstant` emitía esta advertencia. Para corregir los problemas, quite el [`SecurityCritical`] atributo para hacerlos seguridad transparente.

 [!code-csharp[FxCop.Security.CA2130.ConstantsShouldBeTransparent#1](../code-quality/codesnippet/CSharp/ca2130-security-critical-constants-should-be-transparent_1.cs)]