---
title: CommandPlacement (elemento) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- CommandPlacements element (VSCT XML schema)
- VSCT XML schema elements, CommandPlacements
ms.assetid: 2cbd7ac8-c55a-43d8-a26d-713b3d790016
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3c43dab922d51d2d3f96ffaba0ef24f8f0e18fa1
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "66341877"
---
# <a name="commandplacement-element"></a>CommandPlacement (elemento)
CommandPlacement (elemento) permite a los botones, grupos y los menús que se incluirán en más de un grupo o menú. Mediante el uso de CommandPlacement (elemento), no es necesario redefinir completamente estos elementos con el fin de modificar la apariencia de una interfaz de usuario.

 Para obtener más información, consulte [crear grupos reutilizables de botones](../extensibility/creating-reusable-groups-of-buttons.md).

## <a name="syntax"></a>Sintaxis

```
<CommandPlacement guid="guidMyCommandSet" id="MyCommand" priority="0x001" >
  <Parent>... </Parent>
</CommandPlacement>
```

## <a name="attributes-and-elements"></a>Atributos y elementos
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|guid|Obligatorio. El guid del conjunto de comandos, tal como se define en el [Symbols (elemento)](../extensibility/symbols-element.md).|
|id|Obligatorio. El identificador del menú, grupo o comando colocarse, tal como se define en el `Symbols Element`.|
|priority|Obligatorio. Determina la posición del elemento visual en su elemento primario.|
|Condición|Opcional. Consulte [Aattributes condicional](../extensibility/vsct-xml-schema-conditional-attributes.md).|

### <a name="child-elements"></a>Elementos secundarios

|Elemento|Descripción|
|-------------|-----------------|
|Primario|Obligatorio. El menú o el grupo que hospeda el elemento que se va a colocar.|

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|[CommandPlacements (elemento)](../extensibility/commandplacements-element.md)|Especifica los grupos de elementos CommandPlacements y CommandPlacement.|

## <a name="example"></a>Ejemplo

```
<CommandPlacements>
  <CommandPlacement guid="guidWidgetPackage" id="cmdidInsertOptions"
    priority="0x0300">
    <Parent guid="cmdGuidWidgetCommands" id="menuIDEditWidget"/>
  </CommandPlacement>
</CommandPlacements>
```

## <a name="see-also"></a>Vea también
- [CommandPlacements (elemento)](../extensibility/commandplacements-element.md)
- [Archivos visuales Studio comando table (.vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
