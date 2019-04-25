---
title: Propiedades de los decoradores
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, decorators
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 76129141ed293281eeb3179a654f470bcf608bdf
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55907586"
---
# <a name="properties-of-decorators"></a>Propiedades de los decoradores
Los elementos Decorator son iconos, texto o expandir o contraer comillas angulares que pueden aparecer en formas o conectores en el diagrama. Las siguientes tablas muestran las propiedades de los tres tipos de elemento decorator. Algunas de las propiedades aparecen sólo en shape elementos Decorator o sólo en los elementos Decorator del conector.

 Para obtener más información, consulte [cómo definir lenguajes específicos de dominio](../modeling/how-to-define-a-domain-specific-language.md). Para obtener más información sobre cómo usar estas propiedades, vea [personalizar y ampliar lenguajes específicos de dominio](../modeling/customizing-and-extending-a-domain-specific-language.md).

## <a name="expandcollapse-decorator"></a>Expandir o contraer el elemento Decorator

|Property|Descripción|Default|
|-|-|-|
|DisplayName|El nombre del elemento decorator que se mostrará en el diseñador generado.|Expanda el elemento Decorator de contraer|
|nombre|El nombre del elemento decorator.|ExpandCollapseDecorator|
|Notas|Notas informales que están asociadas con este elemento decorator.|\<none>|
|HorizontalOffset|El desplazamiento horizontal, en relación con la posición predeterminada del elemento decorator, en pulgadas. (En formas sólo.)|0|
|VerticalOffset|El desplazamiento vertical, en relación con la posición predeterminada del elemento decorator, en pulgadas. (En formas sólo.)|0|
|OffsetFromLine|El desplazamiento del elemento decorator desde la línea, en relación con su posición predeterminada, en pulgadas. (En los conectores solo.)|0|
|OffsetFromShape|El desplazamiento del elemento decorator desde la forma respecto a su posición predeterminada, en pulgadas. (En los conectores solo.)|0|
|Posición|La posición predeterminada del decorador.|SourceTop|

## <a name="icon-decorator"></a>Elemento Decorator de icono

|Property|Descripción|Default|
|-|-|-|
|DefaultIcon|La ruta de acceso del archivo de icono o imagen que se mostrará.|\<none>|
|DisplayName|El nombre del elemento decorator que se mostrará en el diseñador generado.|Elemento Decorator de icono|
|nombre|El nombre del elemento decorator.|IconDecorator|
|Notas|Notas informales que están asociadas con el elemento decorator.|\<none>|
|HorizontalOffset|El desplazamiento horizontal, en relación con la posición predeterminada del elemento decorator, en pulgadas. (En formas sólo.)|0|
|VerticalOffset|El desplazamiento vertical, en relación con la posición predeterminada del elemento decorator, en pulgadas. (En formas sólo.)|0|
|OffsetFromLine|El desplazamiento del elemento decorator desde la línea, en relación con su posición predeterminada, en pulgadas. (En los conectores solo.)|0|
|OffsetFromShape|El desplazamiento del elemento decorator desde la forma respecto a su posición predeterminada, en pulgadas. (En los conectores solo.)|0|
|Posición|La posición predeterminada del decorador.|SourceTop|

## <a name="textdecorator"></a>TextDecorator

|Property|Descripción|Default|
|-|-|-|
|DefaultText|El texto predeterminado que se mostrará.|Etiqueta|
|DisplayName|El nombre del elemento decorator que se mostrará en el diseñador generado.|Etiqueta|
|FontSize|El tamaño de fuente del texto que se muestra en el elemento decorator.|8|
|FontStyle|El estilo de fuente del texto que se muestra en el elemento decorator.|Estándar|
|nombre|El nombre del elemento decorator.|Etiqueta|
|Notas|Notas informales que están asociadas con el elemento decorator.|\<none>|
|HorizontalOffset|El desplazamiento horizontal, en relación con la posición predeterminada del elemento decorator, en pulgadas. (En formas sólo.)|0|
|VerticalOffset|El desplazamiento vertical, en relación con la posición predeterminada del elemento decorator, en pulgadas. (En formas sólo.)|0|
|OffsetFromLine|El desplazamiento del elemento decorator desde la línea, en relación con su posición predeterminada, en pulgadas. (En los conectores solo.)|0|
|OffsetFromShape|El desplazamiento del elemento decorator desde la forma respecto a su posición predeterminada, en pulgadas. (En los conectores solo.)|0|
|Posición|La posición predeterminada del decorador.|TargetBottom|

## <a name="see-also"></a>Vea también

- [Glosario de las Herramientas del lenguaje específico de dominio](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)