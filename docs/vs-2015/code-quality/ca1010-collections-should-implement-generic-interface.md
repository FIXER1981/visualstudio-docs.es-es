---
title: 'CA1010: las colecciones deben implementar la interfaz genérica | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1010
- CollectionsShouldImplementGenericInterface
helpviewer_keywords:
- CA1010
- CollectionsShouldImplementGenericInterface
ms.assetid: c7d7126f-fa70-40be-8f93-3243e1760dc5
caps.latest.revision: 26
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: b141d755c717ad6650d2a49c98c2b26547066b7a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "85545527"
---
# <a name="ca1010-collections-should-implement-generic-interface"></a>CA1010: Las colecciones deben implementar la interfaz genérica
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Elemento|Value|
|-|-|
|TypeName|CollectionsShouldImplementGenericInterface|
|Identificador de comprobación|CA1010|
|Category|Microsoft. Design|
|Cambio problemático|Poco problemático|

## <a name="cause"></a>Causa
 Un tipo visible externamente implementa la <xref:System.Collections.IEnumerable?displayProperty=fullName> interfaz, pero no implementa la <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> interfaz, y el ensamblado que contiene los destinos [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)] . Esta regla omite los tipos que implementan <xref:System.Collections.IDictionary?displayProperty=fullName> .

## <a name="rule-description"></a>Descripción de la regla
 Para ampliar la utilidad de una colección, implemente una de las interfaces de colección genéricas. A continuación, la colección se puede usar para rellenar tipos de colección genéricos como los siguientes:

- <xref:System.Collections.Generic.List%601?displayProperty=fullName>

- <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>

- <xref:System.Collections.Generic.Stack%601?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones
 Para corregir una infracción de esta regla, implemente una de las interfaces de colección genéricas siguientes:

- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>

- <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>

- <xref:System.Collections.Generic.IList%601?displayProperty=fullName>

## <a name="when-to-suppress-warnings"></a>Cuándo suprimir advertencias
 Es seguro suprimir una advertencia de esta regla. sin embargo, la colección tendrá un uso más limitado.

## <a name="example-violation"></a>Ejemplo de infracción

### <a name="description"></a>Descripción
 En el ejemplo siguiente se muestra una clase (tipo de referencia) que se deriva de la `CollectionBase` clase no genérica, que infringe esta regla.

### <a name="code"></a>Código
 [!code-csharp[FxCop.Design.CollectionsGenericViolation#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.CollectionsGenericViolation/cs/FxCop.Design.CollectionsGenericViolation.cs#1)]

### <a name="comments"></a>Comentarios
 Para corregir una infracción de esta infracción, debe implementar las interfaces genéricas o cambiar la clase base a un tipo que ya implementa las interfaces genéricas y no genéricas, como la `Collection<T>` clase.

## <a name="fix-by-base-class-change"></a>Corregir por cambio de clase base

### <a name="description"></a>Descripción
 En el ejemplo siguiente se corrige la infracción mediante el cambio de la clase base de la colección de la clase no genérica `CollectionBase` a la `Collection<T>` clase genérica ( `Collection(Of T)` en [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ).

### <a name="code"></a>Código
 [!code-csharp[FxCop.Design.CollectionsGenericBase#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.CollectionsGenericBase/cs/FxCop.Design.CollectionsGenericBase.cs#1)]

### <a name="comments"></a>Comentarios
 Cambiar la clase base de una clase ya liberada se considera un cambio importante para los consumidores existentes.

## <a name="fix-by-interface-implementation"></a>Corrección por implementación de interfaz

### <a name="description"></a>Descripción
 En el ejemplo siguiente se corrige la infracción mediante la implementación de estas interfaces genéricas: `IEnumerable<T>` , `ICollection<T>` y `IList<T>` ( `IEnumerable(Of T)` , `ICollection(Of T)` y `IList(Of T)` en [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ).

### <a name="code"></a>Código
 [!code-csharp[FxCop.Design.CollectionsGenericInterface#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.CollectionsGenericInterface/cs/FxCop.Design.CollectionsGenericInterface.cs#1)]

## <a name="related-rules"></a>Reglas relacionadas
 [CA1005: Evitar los parámetros excesivos en tipos genéricos](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1000: No declarar miembros estáticos en tipos genéricos](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: No exponer listas genéricas](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: No anidar tipos genéricos en signaturas de miembro](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004: Los métodos genéricos deben proporcionar un parámetro de tipo](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003: Utilizar instancias genéricas de controlador de eventos](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007: Utilizar valores genéricos cuando sea posible](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>Consulte también
 [Genéricos](https://msdn.microsoft.com/library/75ea8509-a4ea-4e7a-a2b3-cf72482e9282)
