---
title: 'CA2211: los campos no constantes no deben ser visibles | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2211
- NonConstantFieldsShouldNotBeVisible
helpviewer_keywords:
- NonConstantFieldsShouldNotBeVisible
- CA2211
ms.assetid: e1e42c40-0acd-4312-af29-70133739a304
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: aa67c33eac5d618c0a080323720775beea7b68c3
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "85548218"
---
# <a name="ca2211-non-constant-fields-should-not-be-visible"></a>CA2211: Los campos no constantes no deben ser visibles
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Elemento|Value|
|-|-|
|TypeName|NonConstantFieldsShouldNotBeVisible|
|Identificador de comprobación|CA2211|
|Category|Microsoft. Usage|
|Cambio problemático|Problemático|

## <a name="cause"></a>Causa
 Un campo estático público o protegido no es constante ni es de solo lectura.

## <a name="rule-description"></a>Descripción de la regla
 Los campos estáticos que no son constantes ni de sólo lectura no son seguros para subprocesos. El acceso a este tipo de campo debe controlarse cuidadosamente y requiere técnicas de programación avanzada para sincronizar el acceso al objeto de clase. Dado que estos son conocimientos difíciles de aprender y dominar, y probar este tipo de objeto plantea sus propios desafíos, los campos estáticos se utilizan mejor para almacenar datos que no cambian. Esta regla se aplica a las bibliotecas; las aplicaciones no deben exponer ningún campo.

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones
 Para corregir una infracción de esta regla, haga que la constante del campo estático o sea de solo lectura. Si esto no es posible, vuelva a diseñar el tipo para utilizar un mecanismo alternativo, como una propiedad segura para subprocesos que administra el acceso seguro para subprocesos al campo subyacente. Tenga en cuentan que los problemas como la contención de bloqueos y los interbloqueos pueden afectar al rendimiento y el comportamiento de la biblioteca.

## <a name="when-to-suppress-warnings"></a>Cuándo suprimir advertencias
 Es seguro suprimir una advertencia de esta regla si está desarrollando una aplicación y, por tanto, tiene control total sobre el acceso al tipo que contiene el campo estático. Los diseñadores de bibliotecas no deben suprimir una advertencia de esta regla. el uso de campos estáticos no constantes puede hacer que el uso de la biblioteca sea difícil para los desarrolladores.

## <a name="example"></a>Ejemplo
 En el ejemplo siguiente se muestra un tipo que infringe esta regla.

 [!code-csharp[FxCop.Usage.AvoidStaticNonConstants#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.AvoidStaticNonConstants/cs/FxCop.Usage.AvoidStaticNonConstants.cs#1)]
 [!code-vb[FxCop.Usage.AvoidStaticNonConstants#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.AvoidStaticNonConstants/vb/FxCop.Usage.AvoidStaticNonConstants.vb#1)]
