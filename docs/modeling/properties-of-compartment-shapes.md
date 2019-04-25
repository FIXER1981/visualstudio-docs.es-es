---
title: Propiedades de las formas de compartimiento
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.compartmentshape
helpviewer_keywords:
- Domain-Specific Language, compartment shape
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b44b32f98406e4692de97562bbf97e2656b3a7de
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55937388"
---
# <a name="properties-of-compartment-shapes"></a>Propiedades de las formas de compartimiento
Formas de compartimiento son una de las formas que puede usar para mostrar una clase de dominio en un lenguaje específico de dominio. Puede expandir y contraer los compartimientos.

 Para obtener más información, consulte [cómo definir lenguajes específicos de dominio](../modeling/how-to-define-a-domain-specific-language.md). Para obtener más información sobre cómo usar estas propiedades, vea [personalizar y ampliar lenguajes específicos de dominio](../modeling/customizing-and-extending-a-domain-specific-language.md).

 Formas de compartimiento tienen las propiedades que aparecen en la tabla siguiente.

|Property|Descripción|Default|
|-|-|-|
|Predeterminado expandir el estado de contracción|Si `Expanded`, los compartimientos se muestran en la creación. Si `Collapsed`, no lo son.|Expandido|
|Color de relleno|El color de relleno de esta forma.|Blanco|
|Modo de degradado de relleno|El modo de degradado de relleno de esta forma.|Horizontal|
|geometría|La geometría de esta forma (rectángulo o rectángulo redondeado).|Rectángulo|
|Tiene puntos de conexión predeterminada|Si `True`, la forma usará superior, inferior, izquierda y de puntos de conexión adecuado en el diseñador generado.|False|
|Está Visible el encabezado de compartimiento único|Si `False`y la forma tiene un único compartimiento, el encabezado del compartimiento no está visible.|True|
|Color del contorno|El color del contorno de esta forma.|Negro|
|Estilo de guión del contorno|El estilo de guión del contorno de esta forma (sólido, guión, punto, DashDot, DashDotDot, personalizado).|Sólido|
|Grosor del contorno|El grosor del contorno de esta forma.|0.03125|
|Color del texto|El color usado para los elementos Decorator de texto que están asociados con esta forma.|Negro|
|Modificador de acceso|El nivel de acceso de la forma de compartimiento (`public` o `internal`).|Public|
|Atributos personalizados|Utilizado para agregar atributos a la clase de código fuente que se genera a partir de esta forma de compartimiento|\<none>|
|Genera doble derivada|Si `True`, se generará una clase base y una clase parcial (para admitir la personalización mediante invalidaciones). Para obtener más información, consulte [invalidar y ampliar las clases generadas](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|No tiene Constructor personalizado|Si `True`, se proporcionará un constructor personalizado en el código fuente. Para obtener más información, consulte [invalidar y ampliar las clases generadas](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Modificador de herencia|Describe el tipo de herencia de la clase de código fuente que se genera a partir de la forma de compartimiento (`none`, `abstract` o `sealed`).|Ninguna|
|Forma de compartimiento base|La clase base de esta forma.|(ninguno)|
|nombre|El nombre de esta forma.|Nombre actual|
|Espacio de nombres|El espacio de nombres que está asociado a esta forma.|Espacio de nombres actual|
|Tipo de información sobre herramientas|Cómo se define la información sobre herramientas (fijo, variable o ninguno). Si se ha corregido, a continuación, el valor de la `Fixed Tooltip Text` propiedad se utiliza como la información sobre herramientas; si la variable, la información sobre herramientas se define mediante código personalizado.|ninguna|
|Notas|Notas informales que están asociadas con esta forma.|\<none>|
|Alto inicial|Alto inicial de esta forma, en pulgadas. Las formas de compartimiento, esto es el alto de la sección de encabezado solo y no puede cambiarse.|1|
|Ancho inicial|Ancho inicial de esta forma, en pulgadas.|1.5|
|Color de relleno expuestos como propiedad<br /><br /> Modo de degradado de relleno expuestos<br /><br /> Color del contorno puede exponer como propiedad<br /><br /> Estilo de guión del contorno puede exponer como propiedad<br /><br /> Expone el grosor del contorno como propiedad<br /><br /> Expone el Color del texto|Si `True`, el usuario puede establecer la propiedad indicada de una forma. Para ello, haga clic en la definición de la forma y haga clic en **agregar expuestos**.|False|
|Descripción|Se usa para documentar el diseñador generado.|\<none>|
|Nombre para mostrar|El nombre que se mostrará en el diseñador generado para esta forma.|\<none>|
|Texto de información sobre herramientas fijo|El texto que se usa para una información sobre herramientas fija.|\<none>|
|Help Keyword|La palabra clave que se utiliza para indizar la Ayuda F1 para esta forma.|\<none>|

## <a name="see-also"></a>Vea también

- [Glosario de las Herramientas del lenguaje específico de dominio](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)