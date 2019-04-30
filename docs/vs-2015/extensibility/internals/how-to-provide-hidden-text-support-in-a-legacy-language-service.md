---
title: Procedimiento Proporcionar compatibilidad con texto oculto en un servicio de lenguaje heredado | Documentos de Microsoft
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- hidden text, supporting
- editors [Visual Studio SDK], hidden text
- language services, implementing hidden text regions
ms.assetid: 1c1dce9f-bbe2-4fc3-a736-5f78a237f4cc
caps.latest.revision: 22
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 82b8ae72fec0d13eb9da9226945d9a55b60ce186
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "63436162"
---
# <a name="how-to-provide-hidden-text-support-in-a-legacy-language-service"></a>Procedimiento Provisión de compatibilidad con texto oculto en un servicio de lenguaje heredado
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Puede crear áreas de texto oculto además de regiones de esquema. Regiones de texto oculto pueden ser controlado por el cliente o controlado por el editor y se utilizan para ocultar una región de texto completo. El editor muestra una región oculta como líneas horizontales. Un ejemplo de esto es la vista sólo Script en el editor HTML.  
  
## <a name="procedure"></a>Procedimiento  
  
#### <a name="to-implement-a-hidden-text-region"></a>Para implementar una región de texto oculto  
  
1. Llame a `QueryService` para <xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager>.  
  
     Esto devuelve un puntero a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager>.  
  
2. Llamar a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.GetHiddenTextSession%2A>, pasando un puntero para un búfer de texto. Esto determina si una sesión de texto oculto ya existe para el búfer.  
  
3. Si ya existe uno, entonces no es necesario crear uno y un puntero a la existente <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> se devuelve el objeto. Use este puntero para enumerar y crear áreas de texto oculto. En caso contrario, llame a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.CreateHiddenTextSession%2A> para crear una sesión de texto oculto para el búfer.  
  
     Un puntero a la <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> se devuelve el objeto.  
  
    > [!NOTE]
    > Cuando se llama a `CreateHiddenTextSession`, puede especificar un cliente de texto oculto (es decir, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextClient>). El cliente de texto oculto le avisa cuando el texto oculto o esquematización está expandida o contraída por el usuario.  
  
4. Llame a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession.AddHiddenRegions%2A> para agregar uno o más nuevo de esquema regiones a la vez, especificando la siguiente información en el `reHidReg` (<xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion>) parámetro:  
  
    1. Especifique un valor de `hrtConcealed` en el `iType` miembro de la <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> estructura para indicar que va a crear una región oculta, en lugar de una región de esquema.  
  
        > [!NOTE]
        > Cuando se ocultan ocultadas regiones, el editor muestra automáticamente las líneas en torno a las regiones ocultas para indicar su presencia.  
  
    2. Especifique si la región está controlado por el cliente o controlado por el editor en el `dwBehavior` los miembros de la <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> estructura. La implementación de esquematización inteligente puede contener una combinación de las áreas de texto oculto y controlado por el cliente y el editor de esquema.
