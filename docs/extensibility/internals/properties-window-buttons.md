---
title: Botones de la ventana Propiedades | Documentos de Microsoft
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Properties window, buttons
ms.assetid: bdd2e3a7-ae6e-4e88-be1a-e0e3b7ddbbcc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e7726fe13c90c3a2732b7a6131ae4093a9051a62
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56625652"
---
# <a name="properties-window-buttons"></a>Botones de la ventana Propiedades
Según el lenguaje de desarrollo y el tipo de producto, ciertos botones se muestran de forma predeterminada en la barra de herramientas para el **propiedades** ventana. En todos los casos, el **por categorías**, **Alphabetized**, **propiedades**, y **páginas de propiedades** se muestran los botones. En Visual C# y Visual Basic, el **eventos** también se muestra el botón. En determinados proyectos de Visual C++, el **mensajes de VC ++** y **VC invalida** se muestran los botones. Para otros tipos de proyecto se pueden mostrar botones adicionales. Para obtener más información acerca de los botones en la **propiedades** ventana, consulte [ventana propiedades](../../ide/reference/properties-window.md).

## <a name="implementation-of-properties-window-buttons"></a>Implementación de los botones de la ventana Propiedades
 Al hacer clic en el **por categorías** button, llamadas de Visual Studio la <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties> interfaz en el objeto que tiene el foco para ordenar sus propiedades por categoría. <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties> se implementa en el `IDispatch` objeto que se le presenta la **propiedades** ventana.

 Existen 11 categorías de propiedades predefinidas, que tienen valores negativos. Puede definir categorías personalizadas, pero se recomienda asignarles valores positivos para distinguirlas de las categorías predefinidas.

 El <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties.MapPropertyToCategory%2A> método devuelve el valor de categoría de la propiedad adecuada para la propiedad especificada. El <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties.GetCategoryName%2A> método devuelve una cadena que contiene el nombre de categoría. Solo debe proporcionan compatibilidad con valores de categoría personalizada porque Visual Studio conoce los valores de categoría de propiedad estándar.

 Al hacer clic en el **Alphabetized** botón, las propiedades se muestran en orden alfabético por nombre. Los nombres se recuperan por `IDispatch` según un algoritmo de ordenación localizado.

 Cuando el **propiedades** ventana está abierta, el **propiedades** botón se muestra automáticamente como seleccionado. En otras partes del entorno, se muestra el mismo botón, y puede hacer clic para mostrar el **propiedades** ventana.

 El **páginas de propiedades** botón no está disponible si `ISpecifyPropertyPages` no está implementada para el objeto seleccionado. Propiedades dependientes de la configuración de presentación asociados típicamente con soluciones y proyectos de páginas de propiedades, pero se también pueden ser asociados a elementos de proyecto (por ejemplo, en Visual C++).

> [!NOTE]
>  No se puede agregar botones de barra de herramientas a la **propiedades** ventana mediante el uso de código no administrado. Para agregar un botón de barra de herramientas, debe crear un objeto administrado que se deriva de <xref:System.Windows.Forms.Design.PropertyTab>.

## <a name="see-also"></a>Vea también
- [Extensión de propiedades](../../extensibility/internals/extending-properties.md)