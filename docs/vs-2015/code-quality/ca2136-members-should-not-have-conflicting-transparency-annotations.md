---
title: 'CA2136: los miembros no deben tener anotaciones de transparencia en conflicto | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2127
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2136
helpviewer_keywords:
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2127
ms.assetid: ff5a1d18-7c52-4da5-8990-60be83a8ea81
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: a3a17a0db7dd4ad1c57d23104a313a78cd1289ed
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "85547698"
---
# <a name="ca2136-members-should-not-have-conflicting-transparency-annotations"></a>CA2136: Los miembros no deben tener anotaciones de transparencia en conflicto
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Elemento|Value|
|-|-|
|TypeName|TransparencyAnnotationsShouldNotConflict|
|Identificador de comprobación|CA2136|
|Category|Microsoft.Security|
|Cambio problemático|Problemático|

## <a name="cause"></a>Causa
 Esta regla se desencadena cuando un miembro de tipo se marca con un <xref:System.Security> atributo de seguridad que tiene una transparencia diferente que el atributo de seguridad de un contenedor del miembro.

## <a name="rule-description"></a>Descripción de la regla
 Los atributos de transparencia se aplican de los elementos de código de ámbito mayor a los elementos de ámbito menor. Los atributos de transparencia de los elementos de código con mayor ámbito tienen prioridad sobre los atributos de transparencia de los elementos de código incluidos en el primer elemento. Por ejemplo, una clase marcada con el <xref:System.Security.SecurityCriticalAttribute> atributo no puede contener un método marcado con el <xref:System.Security.SecuritySafeCriticalAttribute> atributo.

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones
 Para corregir esta infracción, quite el atributo de seguridad del elemento de código que tiene un ámbito inferior o cambie el atributo para que sea el mismo que el elemento de código contenedor.

## <a name="when-to-suppress-warnings"></a>Cuándo suprimir advertencias
 No suprima las advertencias de esta regla.

## <a name="example"></a>Ejemplo
 En el ejemplo siguiente, un método se marca con el <xref:System.Security.SecuritySafeCriticalAttribute> atributo y es miembro de una clase marcada con el <xref:System.Security.SecurityCriticalAttribute> atributo. Se debe quitar el atributo Safe Security.

 [!code-csharp[FxCop.Security.CA2136.TransparencyAnnotationsShouldNotConflict#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2136.transparencyannotationsshouldnotconflict/cs/ca2136 - transparencyannotationsshouldnotconflict.cs#1)]
