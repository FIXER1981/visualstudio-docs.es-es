---
title: Propiedades de los decoradores | Documentos de Microsoft
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, decorators
ms.assetid: f6322fe5-dc08-4d32-a6b3-0bd18879136d
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d9cd07ed41e39c931e67f43f1c77ff8bd56b2eb3
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65701776"
---
# <a name="properties-of-decorators"></a>Propiedades de los decoradores
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Los elementos Decorator son iconos, texto o expandir o contraer comillas angulares que pueden aparecer en formas o conectores en el diagrama. Las siguientes tablas muestran las propiedades de los tres tipos de elemento decorator. Algunas de las propiedades aparecen sólo en shape elementos Decorator o sólo en los elementos Decorator del conector.  
  
 Para obtener más información, consulte [cómo definir lenguajes específicos de dominio](../modeling/how-to-define-a-domain-specific-language.md). Para obtener más información sobre cómo usar estas propiedades, vea [personalizar y ampliar lenguajes específicos de dominio](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
## <a name="expandcollapse-decorator"></a>Expandir o contraer el elemento Decorator  
  
|Propiedad|Descripción|Default|  
|--------------|-----------------|-------------|  
|DisplayName|El nombre del elemento decorator que se mostrará en el diseñador generado.|Expanda el elemento Decorator de contraer|  
|Name|El nombre del elemento decorator.|ExpandCollapseDecorator|  
|Notas|Notas informales que están asociadas con este elemento decorator.|\<none>|  
|HorizontalOffset|El desplazamiento horizontal, en relación con la posición predeterminada del elemento decorator, en pulgadas. (En formas sólo.)|0|  
|VerticalOffset|El desplazamiento vertical, en relación con la posición predeterminada del elemento decorator, en pulgadas. (En formas sólo.)|0|  
|OffsetFromLine|El desplazamiento del elemento decorator desde la línea, en relación con su posición predeterminada, en pulgadas. (En los conectores solo.)|0|  
|OffsetFromShape|El desplazamiento del elemento decorator desde la forma respecto a su posición predeterminada, en pulgadas. (En los conectores solo.)|0|  
|Posición|La posición predeterminada del decorador.|SourceTop|  
  
## <a name="icon-decorator"></a>Elemento Decorator de icono  
  
|Propiedad|Descripción|Default|  
|--------------|-----------------|-------------|  
|DefaultIcon|La ruta de acceso del archivo de icono o imagen que se mostrará.|\<none>|  
|DisplayName|El nombre del elemento decorator que se mostrará en el diseñador generado.|Elemento Decorator de icono|  
|Name|El nombre del elemento decorator.|IconDecorator|  
|Notas|Notas informales que están asociadas con el elemento decorator.|\<none>|  
|HorizontalOffset|El desplazamiento horizontal, en relación con la posición predeterminada del elemento decorator, en pulgadas. (En formas sólo.)|0|  
|VerticalOffset|El desplazamiento vertical, en relación con la posición predeterminada del elemento decorator, en pulgadas. (En formas sólo.)|0|  
|OffsetFromLine|El desplazamiento del elemento decorator desde la línea, en relación con su posición predeterminada, en pulgadas. (En los conectores solo.)|0|  
|OffsetFromShape|El desplazamiento del elemento decorator desde la forma respecto a su posición predeterminada, en pulgadas. (En los conectores solo.)|0|  
|Posición|La posición predeterminada del decorador.|SourceTop|  
  
## <a name="textdecorator"></a>TextDecorator  
  
|Propiedad|Descripción|Default|  
|--------------|-----------------|-------------|  
|DefaultText|El texto predeterminado que se mostrará.|Etiqueta|  
|DisplayName|El nombre del elemento decorator que se mostrará en el diseñador generado.|Etiqueta|  
|FontSize|El tamaño de fuente del texto que se muestra en el elemento decorator.|8|  
|FontStyle|El estilo de fuente del texto que se muestra en el elemento decorator.|Estándar|  
|Name|El nombre del elemento decorator.|Etiqueta|  
|Notas|Notas informales que están asociadas con el elemento decorator.|\<none>|  
|HorizontalOffset|El desplazamiento horizontal, en relación con la posición predeterminada del elemento decorator, en pulgadas. (En formas sólo.)|0|  
|VerticalOffset|El desplazamiento vertical, en relación con la posición predeterminada del elemento decorator, en pulgadas. (En formas sólo.)|0|  
|OffsetFromLine|El desplazamiento del elemento decorator desde la línea, en relación con su posición predeterminada, en pulgadas. (En los conectores solo.)|0|  
|OffsetFromShape|El desplazamiento del elemento decorator desde la forma respecto a su posición predeterminada, en pulgadas. (En los conectores solo.)|0|  
|Posición|La posición predeterminada del decorador.|TargetBottom|  
  
## <a name="see-also"></a>Vea también  
 [Glosario de las Herramientas del lenguaje específico de dominio](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
