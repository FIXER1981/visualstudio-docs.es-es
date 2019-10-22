---
title: 'CA1059: los miembros no deben exponer determinados tipos concretos | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1059
- MembersShouldNotExposeCertainConcreteTypes
helpviewer_keywords:
- MembersShouldNotExposeCertainConcreteTypes
- CA1059
ms.assetid: 59f61f52-8d6c-49cb-aefb-191910523a3c
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 4c105a1224c405d0be9d74ac6500c875df28604d
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2019
ms.locfileid: "72604041"
---
# <a name="ca1059-members-should-not-expose-certain-concrete-types"></a>CA1059: Los miembros no deben exponer determinados tipos concretos
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MembersShouldNotExposeCertainConcreteTypes|
|Identificador de comprobación|CA1059|
|Categoría|Microsoft. Design|
|Cambio problemático|Problemático|

## <a name="cause"></a>Motivo
 Un miembro visible externamente es un determinado tipo concreto o expone determinados tipos concretos a través de uno de sus parámetros o valor devuelto. Actualmente, esta regla notifica la exposición de los siguientes tipos concretos:

- Tipo derivado de <xref:System.Xml.XmlNode?displayProperty=fullName>.

## <a name="rule-description"></a>Descripción de la regla
 Un tipo concreto es un tipo que tiene una implementación completa y, por consiguiente, se pueden crear instancias de él. Para permitir el uso generalizado del miembro, reemplace el tipo concreto por la interfaz sugerida. Esto permite que el miembro acepte cualquier tipo que implemente la interfaz o se use donde se espera un tipo que implementa la interfaz.

 En la tabla siguiente se enumeran los tipos concretos específicos y sus reemplazos sugeridos.

|Tipo concreto|Replacement|
|-------------------|-----------------|
|<xref:System.Xml.XPath.XPathDocument>|<xref:System.Xml.XPath.IXPathNavigable?displayProperty=fullName>Operador<br /><br /> El uso de la interfaz desacopla el miembro de una implementación concreta de un origen de datos XML.|

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones
 Para corregir una infracción de esta regla, cambie el tipo concreto a la interfaz sugerida.

## <a name="when-to-suppress-warnings"></a>Cuándo suprimir advertencias
 Es seguro suprimir un mensaje de esta regla si se requiere la funcionalidad específica que proporciona el tipo concreto.

## <a name="related-rules"></a>Reglas relacionadas
 [CA1011: Considere pasar los tipos base como parámetros](../code-quality/ca1011-consider-passing-base-types-as-parameters.md)
