---
title: Selección y moneda en el IDE | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- currency, Visual Studio IDE
- IDE, selection
- selection, Visual Studio IDE
- IDE, currency
ms.assetid: 2f6f18d1-acd8-454d-a856-9a4d81155052
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d0a0b999a1a6e6ed2364060031f68378e7222ec0
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68155815"
---
# <a name="selection-and-currency-in-the-ide"></a>Selección y moneda en el IDE
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

El [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] entorno de desarrollo integrado (IDE) mantiene información acerca de los objetos seleccionados actualmente por los usuarios mediante el *contexto*de selección. Con el contexto de selección, los VSPackages pueden participar en el seguimiento de moneda de dos maneras:  
  
- Al propagar la información de moneda sobre los VSPackages al IDE.  
  
- Mediante la supervisión de las selecciones activas de los usuarios en el IDE.  
  
## <a name="selection-context"></a>Contexto de selección  
 El [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE realiza un seguimiento global de la moneda del IDE en su propio objeto de contexto de selección global. En la tabla siguiente se muestran los elementos que componen el contexto de selección.  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|Jerarquía actual|Normalmente, el proyecto actual; una jerarquía actual nula indica que la solución en su conjunto es actual.|  
|ItemID actual|Elemento seleccionado dentro de la jerarquía actual; cuando hay varias selecciones en una ventana de proyecto, puede haber varios elementos actuales.|  
|Corrientes `SelectionContainer`|Contiene uno o más objetos para los que el ventana Propiedades debe mostrar las propiedades.|  
  
 Además, el entorno mantiene dos listas globales:  
  
- Lista de identificadores de comandos de la interfaz de usuario activa  
  
- Lista de los tipos de elemento activos actualmente.  
  
### <a name="window-types-and-selection"></a>Tipos y selección de ventanas  
 El [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE organiza las ventanas en dos tipos generales:  
  
- Jerarquía de tipos de ventanas  
  
- Ventanas de marco, como ventanas de herramientas y de documentos  
  
  El IDE realiza un seguimiento de la moneda de manera diferente para cada uno de estos tipos de ventanas.  
  
  La ventana de tipo de proyecto más común es el explorador de soluciones, que controla el IDE. Una ventana de tipo de proyecto realiza un seguimiento de la jerarquía global y el ItemID del contexto de selección global, y la ventana se basa en la selección del usuario para determinar la jerarquía actual. En el caso de las ventanas de tipo de proyecto, el entorno proporciona el servicio global <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> , a través del cual los VSPackages pueden supervisar los valores actuales de los elementos abiertos. La exploración de propiedades en el entorno está controlada por este servicio global.  
  
  Por otro lado, las ventanas de marco usan el DocObject dentro de la ventana de marco para enviar el valor SelectionContext (Hierarchy/ItemID/SelectionContainer trío). . Las ventanas de marco usan el servicio <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> para este fin. El DocObject solo puede enviar valores para el contenedor de selección, de modo que los valores locales de Hierarchy y ItemID no se modifican, como es habitual en los documentos MDI secundarios.  
  
### <a name="events-and-currency"></a>Eventos y moneda  
 Pueden producirse dos tipos de eventos que afectan a la noción de moneda del entorno:  
  
- Eventos que se propagan al nivel global y cambian el contexto de selección de marcos de ventana. Entre los ejemplos de este tipo de evento se incluye la apertura de una ventana secundaria MDI, la apertura de una ventana de herramientas global o la apertura de una ventana de herramientas de tipo de proyecto.  
  
- Eventos que cambian los elementos de los que se realiza un seguimiento en el contexto de selección de marcos de ventana. Entre los ejemplos se incluye cambiar la selección dentro de un DocObject o cambiar la selección en una ventana de tipo de proyecto.  
  
## <a name="see-also"></a>Consulte también  
 [Objetos de contexto de selección](../../extensibility/internals/selection-context-objects.md)   
 [Comentarios para el usuario](../../extensibility/internals/feedback-to-the-user.md)
