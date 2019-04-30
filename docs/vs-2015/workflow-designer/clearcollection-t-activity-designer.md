---
title: ClearCollection&lt;T&gt; Diseñador de actividad | Documentos de Microsoft
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ClearCollection`1.UI
ms.assetid: db0e5da2-7b5a-4f1a-864c-f3aeeeeb51a7
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 240e634115e7602c66d69f0dba9cfa52504dc89a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62977165"
---
# <a name="clearcollectionlttgt-activity-designer"></a>ClearCollection&lt;T&gt; Diseñador de actividad
El **ClearCollection\<T >** Diseñador de actividad se usa para crear y configurar un <xref:System.Activities.Statements.ClearCollection%601> actividad.  
  
## <a name="the-clearcollectiont-activity"></a>ClearCollection\<T > actividad  
 La actividad <xref:System.Activities.Statements.ClearCollection%601> borra una colección especificada de todos los elementos.  
  
### <a name="using-the-clearcollectiont-activity-designer"></a>Uso de ClearCollection\<T > Diseñador de actividad  
 El **ClearCollection\<T >** Diseñador de actividad puede encontrarse en el **colección** categoría de la **cuadro de herramientas**, que se tiene acceso haciendo clic en el  **Cuadro de herramientas** pestaña de la [!INCLUDE[wfd2](../includes/wfd2-md.md)] (como alternativa, seleccione **barra de herramientas** desde el **vista** menú o CTRL + ALT + X.)  
  
 El **ClearCollection\<T >** Diseñador de actividad se puede arrastrar desde el **cuadro de herramientas** y colocarlo en la [!INCLUDE[wfd2](../includes/wfd2-md.md)] superficie donde se coloquen normalmente las actividades, tal como en un <xref:System.Activities.Statements.Sequence>. Esto crea un <xref:System.Activities.Statements.ClearCollection%601> actividad con un valor predeterminado <xref:System.Activities.Activity.DisplayName%2A> de ClearCollection\<Int32 >. (De forma predeterminada, el *TypeArgument* es **Int32**. Se puede cambiar en la cuadrícula de propiedades). El <xref:System.Activities.Activity.DisplayName%2A> se puede editar en el encabezado de la **ClearCollection\<T >** Diseñador de actividad o en el **DisplayName** cuadro de la cuadrícula de propiedades. Es preciso editar las otras propiedades en la cuadrícula de propiedades.  
  
### <a name="the-clearcollectiont-properties"></a>ClearCollection\<T > Propiedades  
 En la tabla siguiente se muestran las propiedades <xref:System.Activities.Statements.ClearCollection%601> y se describe cómo se utilizan en el diseñador.  
  
|Nombre de la propiedad|Obligatorio|Uso|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Especifica el nombre opcional descriptivo de la actividad <xref:System.Activities.Statements.ClearCollection%601>. El valor predeterminado es ClearCollection\<Int32 >. Pese a que el valor <xref:System.Activities.Activity.DisplayName%2A> no es obligatorio, se recomienda usar uno.|  
|<xref:System.Activities.Statements.ClearCollection%601.Collection%2A>|True|Especifica la recopilación que se va a borrar de los elementos. Esta colección es de tipo **ICollection\<TypeArgument >.** Para especificar la colección, escriba una expresión de Visual Basic en la cuadrícula de propiedades.|  
|*TypeArgument*|True|Especifica el tipo T de los elementos contenidos en <xref:System.Collections.Generic.ICollection%601>. De forma predeterminada, esto *TypeArgument* tipo está establecido en **Int32**. Para cambiar el tipo, cambie el valor de la *TypeArgument* en el cuadro combinado en la cuadrícula de propiedades.|  
  
## <a name="see-also"></a>Vea también  
 [colección](../workflow-designer/collection-activity-designers.md)   
 [AddToCollection\<T>](../workflow-designer/addtocollection-t-activity-designer.md)   
 [ExistsInCollection\<T>](../workflow-designer/existsincollection-t-activity-designer.md)   
 [RemoveFromCollection\<T>](../workflow-designer/removefromcollection-t-activity-designer.md)