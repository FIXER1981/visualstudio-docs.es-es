---
title: 'CA1048: no declarar miembros virtuales en tipos sellados | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotDeclareVirtualMembersInSealedTypes
- CA1048
helpviewer_keywords:
- DoNotDeclareVirtualMembersInSealedTypes
- CA1048
ms.assetid: 5dcf4a30-6f98-48a8-b8cc-7b89ea757262
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 19ae3a4fdc620343f18aa0845c33e1d73529adfe
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "85546801"
---
# <a name="ca1048-do-not-declare-virtual-members-in-sealed-types"></a>CA1048: No declarar miembros virtuales en tipos sellados
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Elemento|Value|
|-|-|
|TypeName|DoNotDeclareVirtualMembersInSealedTypes|
|Identificador de comprobación|CA1048|
|Category|Microsoft. Design|
|Cambio problemático|Problemático|

## <a name="cause"></a>Causa
 Un tipo público está sellado y declara un método que es Both `virtual` ( `Overridable` en Visual Basic) y no final. Esta regla no notifica las infracciones de los tipos de delegado, que deben seguir este patrón.

## <a name="rule-description"></a>Descripción de la regla
 Los tipos declaran los métodos como virtuales para que los tipos heredados puedan reemplazar la implementación del método virtual. Por definición, no se puede heredar de un tipo sellado, lo que hace que un método virtual en un tipo sellado no tenga sentido.

 Los compiladores de Visual Basic .NET y C# no permiten a los tipos infringir esta regla.

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones
 Para corregir una infracción de esta regla, haga que el método sea no virtual o haga que el tipo sea heredable.

## <a name="when-to-suppress-warnings"></a>Cuándo suprimir advertencias
 No suprima las advertencias de esta regla. Si se deja el tipo en su estado actual, se pueden producir problemas de mantenimiento y no se proporciona ninguna ventaja.

## <a name="example"></a>Ejemplo
 En el ejemplo siguiente se muestra un tipo que infringe esta regla.

 [!code-cpp[FxCop.Design.SealedVirtual#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.SealedVirtual/cpp/FxCop.Design.SealedVirtual.cpp#1)]
