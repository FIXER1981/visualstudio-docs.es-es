---
title: Elemento UsedCommand | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- UsedCommands element (VSCT XML schema)
- VSCT XML schema elements, UsedCommands
ms.assetid: 99cd05d3-644a-42ff-b289-8458cd1b20c0
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 65030c3fe24c3456b0c4c99a667362d2a4c67703
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80698826"
---
# <a name="usedcommand-element"></a>UsedCommand (Elemento)
Permite a un VSPackage obtener acceso a un comando que se define en otro archivo. Vsct. Por ejemplo, si el VSPackage usa el comando de **copia** estándar, que se define mediante el [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Shell, puede Agregar el comando a un menú o barra de herramientas sin volver a implementarlo.

## <a name="syntax"></a>Sintaxis

```
<UsedCommand guid="guidMyCommandGroup" id="MyCommand" />
```

## <a name="attributes-and-elements"></a>Atributos y elementos
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|guid|Necesario. GUID del par de IDENTIFICADOres GUID que identifica el comando.|
|id|Necesario. IDENTIFICADOR del par de IDENTIFICADOres GUID que identifica el comando.|
|Condición|Opcional. Vea [atributos condicionales](../extensibility/vsct-xml-schema-conditional-attributes.md).|

### <a name="child-elements"></a>Elementos secundarios

|Elemento|Descripción|
|-------------|-----------------|
|None||

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|[UsedCommands (Elemento)](../extensibility/usedcommands-element.md)|Agrupa los elementos UsedCommand y otras agrupaciones UsedCommands.|

## <a name="remarks"></a>Observaciones
 Al agregar un comando al `<UsedCommands>` elemento, un VSPackage informa al [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] entorno de que el VSPackage requiere el comando. Debe agregar un `<UsedCommand>` elemento para cualquier comando que el paquete requiera y que no esté incluido en todas las versiones y configuraciones de Visual Studio. Por ejemplo, si el paquete llama a un comando específico de Visual C++, el comando no estará disponible para los usuarios de Visual Web Developer a menos que incluya un `<UsedCommand>` elemento para el comando.

## <a name="example"></a>Ejemplo

```
<UsedCommands>
  <UsedCommand guid="guidVSStd97" id="cmdidCut"/>
  <UsedCommand guid="guidVSStd97" id="cmdidCopy"/>
  <UsedCommand guid="guidVSStd97" id="cmdidPaste"/>
</UsedCommands>
```

## <a name="see-also"></a>Vea también
- [UsedCommands (Elemento)](../extensibility/usedcommands-element.md)
- [Archivos de tabla de comandos de Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
