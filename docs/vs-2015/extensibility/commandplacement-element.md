---
title: Elemento CommandPlacement | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- CommandPlacements element (VSCT XML schema)
- VSCT XML schema elements, CommandPlacements
ms.assetid: 2cbd7ac8-c55a-43d8-a26d-713b3d790016
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 43fd417c4d54c0ab57133cf6dbff2c770c1ffc45
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68184335"
---
# <a name="commandplacement-element"></a>CommandPlacement (Elemento)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

El elemento CommandPlacement permite incluir botones, grupos y menús en más de un grupo o menú. Al usar el elemento CommandPlacement, no es necesario volver a definir completamente estos elementos para modificar el aspecto de una interfaz de usuario.  
  
 Para obtener más información, vea [crear grupos reutilizables de botones](../extensibility/creating-reusable-groups-of-buttons.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
<CommandPlacement guid=guidMyCommandSet" id="MyCommand" priority="0x001" >  
  <Parent>... </Parent>  
</CommandPlacement>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|guid|Necesario. GUID del conjunto de comandos, tal y como se define en el [elemento Symbols](../extensibility/symbols-element.md).|  
|id|Necesario. Identificador del menú, grupo o comando que se va a colocar, tal como se define en `Symbols Element` .|  
|priority|Necesario. Determina la posición visual del elemento en su elemento primario.|  
|Condición|Opcional. Vea [atributos condicionales](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|Parent|Necesario. Menú o grupo que hospeda el elemento que se va a colocar.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[CommandPlacements (Elemento)](../extensibility/commandplacements-element.md)|Especifica grupos de elementos CommandPlacements y CommandPlacement.|  
  
## <a name="example"></a>Ejemplo  
  
```  
<CommandPlacements>  
  <CommandPlacement guid="guidWidgetPackage" id="cmdidInsertOptions"  
    priority="0x0300">  
    <Parent guid="cmdGuidWidgetCommands" id="menuIDEditWidget"/>  
  </CommandPlacement>  
</CommandPlacements>  
```  
  
## <a name="see-also"></a>Consulte también  
 [Elemento CommandPlacements](../extensibility/commandplacements-element.md)   
 [Archivos de tabla de comandos de Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
