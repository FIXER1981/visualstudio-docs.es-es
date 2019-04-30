---
title: VisibilityItem (elemento) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- VisibilityItem element (VSCT XML schema)
- VSCT XML schema elements, VisibilityItem
ms.assetid: 0932f551-972d-4194-84bb-426e3e4375e4
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f6f71e145282d1d6e340060b9798ca54c9af9f4e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62584851"
---
# <a name="visibilityitem-element"></a>VisibilityItem (Elemento)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

El `VisibilityItem` elemento determina la visibilidad de los comandos y las barras de herramientas estática. Cada entrada identifica un comando o menú y también un contexto de interfaz de usuario de comando asociado. Visual Studio detecta los comandos, menús y barras de herramientas y su visibilidad, sin tener que cargar los VSPackages que definirlas. El IDE usa la <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A> método para determinar si un contexto de interfaz de usuario de comandos está activo.  
  
 Una vez cargado el VSPackage, Visual Studio espera visibilidad comando quedará determinado por el VSPackage en lugar de `VisibilityItem`. Para determinar la visibilidad de los comandos, puede implementar la <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> controlador de eventos o la <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> método, según cómo haya implementado el comando.  
  
 Un comando o un menú que tenga un `VisibilityItem` elemento aparece solo cuando está activo el contexto asociado. Puede asociar un único comando, barra de menús o con uno o más contextos de interfaz de usuario de comandos mediante la inclusión de una entrada para cada combinación de contexto de comandos. Si un comando o un menú está asociado con varios contextos de interfaz de usuario de comandos, a continuación, el comando o el menú es visible cuando cualquiera de los contextos de interfaz de usuario de comando asociado está activo.  
  
 El `VisibilityItem` elemento solo se aplica a los comandos, menús y barras de herramientas, no a los grupos. Un elemento que no tiene un relacionados `VisibilityItem` elemento está visible cuando está activo el menú primario.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
<VisibilityItem  
  guid ="="cmdGuidMyProductCommands"  
  id=="cmdidAddWidget"  
  context="guidNotViewSourceMode"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|guid|Obligatorio. El GUID del identificador de comando/identificador de GUID.|  
|id|Obligatorio. El identificador del identificador de comando/identificador de GUID.|  
|contexto|Obligatorio. El contexto de interfaz de usuario en el que está visible el comando.|  
|Condición|Opcional. Consulte [atributos condicionales](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[VisibilityConstraints (Elemento)](../extensibility/visibilityconstraints-element.md)|El `VisibilityConstraints` elemento determina la visibilidad de los grupos de comandos y las barras de herramientas estática.|  
  
## <a name="remarks"></a>Comentarios  
 Los contextos de interfaz de usuario de Visual Studio estándares se definen en el *ruta de instalación del SDK de Visual Studio*\VisualStudioIntegration\Common\Inc\vsshlids.h archivo así como en el <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids> y <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80> clases. Se define un conjunto más completo de contextos de interfaz de usuario en el <xref:Microsoft.VisualStudio.VSConstants> clase.  
  
## <a name="example"></a>Ejemplo  
  
```  
<VisibilityConstraints>  
  <VisibilityItem guid="cmdSetGuidMyProductCommands"     id="cmdidAddWidget"  
    context="guidNotViewSourceMode"/>  
</VisibilityConstraints>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A>   
 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus>   
 <xref:Microsoft.VisualStudio.VSConstants>   
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids>   
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80>   
 [VisibilityConstraints (elemento)](../extensibility/visibilityconstraints-element.md)   
 [Archivos de tabla de comandos de Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
