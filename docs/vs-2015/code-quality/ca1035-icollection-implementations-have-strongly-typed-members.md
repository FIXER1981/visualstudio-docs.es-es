---
title: 'CA1035: las implementaciones de ICollection tienen miembros fuertemente tipados | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ICollectionImplementationsHaveStronglyTypedMembers
- CA1035
helpviewer_keywords:
- CA1035
- ICollectionImplementationsHaveStronglyTypedMembers
ms.assetid: ad404eb5-cf6a-44b7-b78a-8ebfb654bc7f
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 2e679fb3cc62ba80cfb7b56dfd7fa6590375565e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "85546619"
---
# <a name="ca1035-icollection-implementations-have-strongly-typed-members"></a>CA1035: Las implementaciones de ICollection tienen miembros fuertemente tipados
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Elemento|Value|
|-|-|
|TypeName|ICollectionImplementationsHaveStronglyTypedMembers|
|Identificador de comprobación|CA1035|
|Category|Microsoft. Design|
|Cambio problemático|Problemático|

## <a name="cause"></a>Causa
 Un tipo público o protegido implementa <xref:System.Collections.ICollection?displayProperty=fullName> pero no proporciona un método fuertemente tipado para <xref:System.Collections.ICollection.CopyTo%2A?displayProperty=fullName> . La versión fuertemente tipada de <xref:System.Collections.ICollection.CopyTo%2A> debe aceptar dos parámetros y no puede tener <xref:System.Array?displayProperty=fullName> o una matriz de <xref:System.Object?displayProperty=fullName> como su primer parámetro.

## <a name="rule-description"></a>Descripción de la regla
 Esta regla requiere que las <xref:System.Collections.ICollection> implementaciones proporcionen miembros fuertemente tipados para que los usuarios no tengan que convertir los argumentos al <xref:System.Object> tipo cuando utilicen la funcionalidad proporcionada por la interfaz. Esta regla supone que el tipo que implementa <xref:System.Collections.ICollection> lo hace para administrar una colección de instancias de un tipo que es más seguro que <xref:System.Object> .

 <xref:System.Collections.ICollection> implementa la interfaz <xref:System.Collections.IEnumerable?displayProperty=fullName>. Si los objetos de la colección se extienden <xref:System.ValueType?displayProperty=fullName> , debe proporcionar un miembro fuertemente tipado para <xref:System.Collections.IEnumerable.GetEnumerator%2A> para evitar la disminución del rendimiento que se debe a la conversión boxing. Esto no es necesario cuando los objetos de la colección son un tipo de referencia.

 Para implementar una versión fuertemente tipada de un miembro de interfaz, implemente los miembros de interfaz explícitamente utilizando nombres en el formulario `InterfaceName.InterfaceMemberName` , como <xref:System.Collections.ICollection.CopyTo%2A> . Los miembros de interfaz explícitos usan los tipos de datos declarados por la interfaz. Implemente los miembros fuertemente tipados mediante el nombre del miembro de interfaz, como <xref:System.Collections.ICollection.CopyTo%2A> . Declare los miembros fuertemente tipados como públicos y declare los parámetros y los valores devueltos para que sean del tipo seguro administrado por la colección. Los tipos seguros reemplazan a los tipos más débiles como <xref:System.Object> y <xref:System.Array> que se declaran mediante la interfaz.

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones
 Para corregir una infracción de esta regla, implemente explícitamente el miembro de interfaz (declárela como <xref:System.Collections.ICollection.CopyTo%2A> ). Agregue el miembro con establecimiento inflexible de tipos, declarado como `CopyTo` , y haga que tome una matriz fuertemente tipada como su primer parámetro.

## <a name="when-to-suppress-warnings"></a>Cuándo suprimir advertencias
 Suprima una advertencia de esta regla si implementa una nueva colección basada en objetos, como un árbol binario, donde los tipos que extienden la nueva colección determinan el tipo seguro. Estos tipos deben cumplir esta regla y exponer miembros fuertemente tipados.

## <a name="example"></a>Ejemplo
 En el ejemplo siguiente se muestra la manera correcta de implementar <xref:System.Collections.ICollection> .

 [!code-csharp[FxCop.Design.ICollectionStrongTypes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ICollectionStrongTypes/cs/FxCop.Design.ICollectionStrongTypes.cs#1)]

## <a name="related-rules"></a>Reglas relacionadas
 [CA1038: Los enumeradores deben estar fuertemente tipados](../code-quality/ca1038-enumerators-should-be-strongly-typed.md)

 [CA1039: Las listas están fuertemente tipadas](../code-quality/ca1039-lists-are-strongly-typed.md)

## <a name="see-also"></a>Consulte también
 <xref:System.Array?displayProperty=fullName> <xref:System.Collections.IEnumerable?displayProperty=fullName>
 <xref:System.Collections.ICollection?displayProperty=fullName>
 <xref:System.Object?displayProperty=fullName>
