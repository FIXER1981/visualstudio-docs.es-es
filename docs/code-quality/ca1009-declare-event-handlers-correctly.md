---
title: 'CA1009: Declarar los controladores de evento correctamente'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1009
- DeclareEventHandlersCorrectly
helpviewer_keywords:
- CA1009
- DeclareEventHandlersCorrectly
ms.assetid: ab65c471-1449-49d2-9896-7b9af74284b4
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e923730213ca31a4429d8547fdaaf980692f9a96
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "71236476"
---
# <a name="ca1009-declare-event-handlers-correctly"></a>CA1009: Declarar los controladores de evento correctamente

|||
|-|-|
|TypeName|DeclareEventHandlersCorrectly|
|Identificador de comprobación|CA1009|
|Categoría|Microsoft.Design|
|Cambio importante|Problemático|

## <a name="cause"></a>Motivo
Un delegado que controla un evento público o protegido no tiene la firma, el tipo de valor devuelto o los nombres de parámetro correctos.

## <a name="rule-description"></a>Descripción de la regla
Los métodos de control de eventos toman dos parámetros. El primero es de tipo <xref:System.Object?displayProperty=fullName> y se denomina ' Sender '. Éste es el objeto que provocó el evento. El segundo parámetro es de tipo <xref:System.EventArgs?displayProperty=fullName> y se denomina ' e '. Estos son los datos están asociados a este evento. Por ejemplo, si el evento se genera cada vez que se abre un archivo, los datos del evento normalmente contienen el nombre del archivo.

Los métodos de controlador de eventos no deben devolver un valor. En el C# lenguaje de programación, esto se indica mediante el tipo `void`de valor devuelto. Un controlador de eventos puede invocar varios métodos en varios objetos. Si se permite que los métodos devuelvan un valor, se producirán varios valores devueltos para cada evento y solo estará disponible el valor del último método que se invocó.

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones
Para corregir una infracción de esta regla, corrija la firma, el tipo de valor devuelto o los nombres de parámetro del delegado. Para obtener más información, vea el ejemplo siguiente.

## <a name="when-to-suppress-warnings"></a>Cuándo suprimir advertencias
No suprima las advertencias de esta regla.

## <a name="example"></a>Ejemplo
En el ejemplo siguiente se muestra un delegado adecuado para controlar eventos. Los métodos que puede invocar este controlador de eventos cumplen con la firma que se especifica en las instrucciones de diseño. `AlarmEventHandler`es el nombre de tipo del delegado. `AlarmEventArgs`deriva de la clase base para los datos de evento <xref:System.EventArgs>, y contiene los datos de eventos de alarma.

[!code-cpp[FxCop.Design.EventsTwoParams#1](../code-quality/codesnippet/CPP/ca1009-declare-event-handlers-correctly_1.cpp)]
[!code-csharp[FxCop.Design.EventsTwoParams#1](../code-quality/codesnippet/CSharp/ca1009-declare-event-handlers-correctly_1.cs)]
[!code-vb[FxCop.Design.EventsTwoParams#1](../code-quality/codesnippet/VisualBasic/ca1009-declare-event-handlers-correctly_1.vb)]

## <a name="related-rules"></a>Reglas relacionadas
[CA2109: Revisar los controladores de eventos visibles](../code-quality/ca2109-review-visible-event-handlers.md)

## <a name="see-also"></a>Vea también

- <xref:System.EventArgs?displayProperty=fullName>
- <xref:System.Object?displayProperty=fullName>
- [Control y generación de eventos](/dotnet/standard/events/index)