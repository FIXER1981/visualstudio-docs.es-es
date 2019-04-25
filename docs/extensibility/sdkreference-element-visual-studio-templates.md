---
title: SDKReference (elemento) (plantillas de Visual Studio) | Documentos de Microsoft
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
ms.assetid: 72c8b352-0b7a-42b3-ba5d-2a2d1e90c34b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 692b8600d1de2cbbb17841dd174c4a18010c41d6
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56691168"
---
# <a name="sdkreference-element-visual-studio-templates"></a>SDKReference (Elemento, Plantillas de Visual Studio)
Especifica que la plantilla del elemento usa una referencia de SDK.

## <a name="syntax"></a>Sintaxis

```xml
<VSTemplate>
    <TemplateContent>
        <References>
            <Reference>
                <SDKReference>SDKname</SDKReference>
```

## <a name="attributes-and-elements"></a>Atributos y elementos
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos
 Ninguno.

### <a name="child-elements"></a>Elementos secundarios
 Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|[Referencia](../extensibility/reference-element-visual-studio-templates.md)|Especifica la referencia de ensamblado para agregar cuando el elemento se agrega a un proyecto.|

## <a name="text-value"></a>Valor de texto
 Se requiere un valor de texto.

## <a name="remarks"></a>Comentarios
 Este texto especifica la referencia SDK que se debe agregar a un proyecto cuando se crea una instancia de la plantilla de elemento.

```xml
<VSTemplate Version="3.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">
    <TemplateData> . . . </TemplateData>
    <TemplateContent>
        <References>
            <Reference>
                <SDKReference>Microsoft Visual C++ Runtime Package, Version=11.0.0.0</SDKReference>
...
```

## <a name="see-also"></a>Vea también
- [References (Elemento, Plantillas de Visual Studio)](../extensibility/references-element-visual-studio-templates.md)
- [Reference (Elemento, Plantillas de Visual Studio)](../extensibility/reference-element-visual-studio-templates.md)
- [Crear plantillas para proyectos y elementos en Visual Studio](../ide/creating-project-and-item-templates.md)
- [Referencia de esquema de plantillas de Visual Studio](../extensibility/visual-studio-template-schema-reference.md)