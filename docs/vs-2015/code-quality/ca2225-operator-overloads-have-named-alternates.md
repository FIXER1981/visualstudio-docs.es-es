---
title: 'CA2225: Las sobrecargas del operador tienen alternativas con nombre | Documentos de Microsoft'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- OperatorOverloadsHaveNamedAlternates
- CA2225
helpviewer_keywords:
- OperatorOverloadsHaveNamedAlternates
- CA2225
ms.assetid: af8f7ab1-63ad-4861-afb9-b7a7a2be15e1
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: aa90a1e97b563ef549cb3f628fcf9130a364c50a
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "58997407"
---
# <a name="ca2225-operator-overloads-have-named-alternates"></a>CA2225: Las sobrecargas del operador tienen alternativas con nombre
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|OperatorOverloadsHaveNamedAlternates|
|Identificador de comprobación|CA2225|
|Categoría|Microsoft.Usage|
|Cambio problemático|No trascendental|

## <a name="cause"></a>Motivo
 Se detectó una sobrecarga del operador y no se encontró el método alternativo con el nombre esperado.

## <a name="rule-description"></a>Descripción de la regla
 Sobrecarga de operadores permite el uso de símbolos para representar los cálculos para un tipo. Por ejemplo, un tipo que sobrecarga el símbolo más (+) para la suma normalmente tendría un miembro alternativo denominado 'Add'. El miembro alternativo con nombre proporciona acceso a la misma funcionalidad que el operador y se proporciona para los desarrolladores que programan en lenguajes que no admite operadores sobrecargados.

 Esta regla examina los operadores se indican en la tabla siguiente.

|C#|Visual Basic|C++|Nombre alternativo|
|---------|------------------|-----------|--------------------|
|+ (binario)|+|+ (binario)|Agregar|
|+=|+=|+=|Agregar|
|&|y|&|BitwiseAnd|
|&=|Y =|&=|BitwiseAnd|
|&#124;|O bien|&#124;|BitwiseOr|
|&#124;=|O =|&#124;=|BitwiseOr|
|--|N/D|--|Decremento|
|/|/|/|Dividir|
|/=|/=|/=|Dividir|
|==|=|==|Es igual a|
|^|Xor|^|Xor|
|^=|Xor=|^=|Xor|
|>|>|>|Comparar|
|>=|>=|>=|Comparar|
|++|N/D|++|Incremento|
|<>|!=|Es igual a|
|<<|<<|<<|Izq|
|<<=|<<=|<<=|Izq|
|<|<|<|Comparar|
|<=|<=|\<=|Comparar|
|&&|N/D|&&|LogicalAnd|
|&#124;&#124;|N/D|&#124;&#124;|LogicalOr|
|!|N/D|!|LogicalNot|
|%|Mod|%|Mod o resto|
|%=|N/D|%=|Mod|
|* (binario)|*|*|Multiplicar|
|*=|N/D|*=|Multiplicar|
|~|not|~|OnesComplement|
|>>|>>|>>|DER|
=|N/D|>>=|DER|
|-(binario)|-(binario)|-(binario)|Restar|
|-=|N/D|-=|Restar|
|true|IsTrue|N/D|IsTrue (propiedad)|
|-(unario)|N/D|-|negar|
|+ (unario)|N/D|+|Signo más|
|False|IsFalse|False|IsTrue (propiedad)|

 N/D == no se puede sobrecargar en el idioma seleccionado.

 La regla también comprueba los operadores de conversión implícitos y explícitos en un tipo (`SomeType`) mediante la comprobación de los métodos denominados `ToSomeType` y `FromSomeType`.

 En C#, cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si los hay, también es implícitamente sobrecargado.

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones
 Para corregir una infracción de esta regla, implemente el método alternativo para el operador. asígnele un nombre que el nombre alternativo recomendado.

## <a name="when-to-suppress-warnings"></a>Cuándo suprimir advertencias
 No suprima una advertencia de esta regla si está implementando una biblioteca compartida. Las aplicaciones pueden omitir una advertencia de esta regla.

## <a name="example"></a>Ejemplo
 El ejemplo siguiente define una estructura que infringe esta regla. Para corregir el ejemplo, agregue una pública `Add(int x, int y)` método a la estructura.

 [!code-csharp[FxCop.Usage.OperatorOverloadsHaveNamedAlternates#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OperatorOverloadsHaveNamedAlternates/cs/FxCop.Usage.OperatorOverloadsHaveNamedAlternates.cs#1)]

## <a name="related-rules"></a>Reglas relacionadas
 [CA1046: No sobrecargar el operador de igualdad en los tipos de referencia](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)

 [CA2226: Los operadores deben tener sobrecargar simétricas](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

 [CA2224: Invalidar equals al sobrecargar operadores de igualdad](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)

 [CA2218: Invalidar el método GetHashCode al invalidar Equals](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

 [CA2231: sobrecargar el operador equals al invalidar ValueType.Equals](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)
