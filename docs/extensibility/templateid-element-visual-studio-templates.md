---
title: TemplateID (elemento) (plantillas de Visual Studio) | Documentos de Microsoft
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#TemplateID
helpviewer_keywords:
- <TemplateID> element [Visual Studio Templates]
- TemplateID element [Visual Studio Templates]
ms.assetid: 6ca24b4e-0325-4a9e-855e-0cbbe7361d8f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f1f992d9f501b965fc300b97613a3d6f3bd4e35d
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56680586"
---
# <a name="templateid-element-visual-studio-templates"></a>TemplateID (Elemento, Plantillas de Visual Studio)
Especifica un identificador para una plantilla de elementos que se clasifica por categorías en un grupo de plantillas de elementos por el [TemplateGroupID](../extensibility/templategroupid-element-visual-studio-templates.md) elemento.

 \<VSTemplate> \<TemplateData> \<TemplateID>

## <a name="syntax"></a>Sintaxis

```
<TemplateID> ... </TemplateID>
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Elemento necesario.<br /><br /> Clasifica la plantilla y define cómo se muestra en el cuadro de diálogo **Nuevo proyecto** o **Agregar nuevo elemento** .|

## <a name="text-value"></a>Valor de texto
 Un `string` que representa un identificador para una plantilla de elementos que se clasifica por categorías en un grupo de plantillas de elementos por el `TemplateGroupID` elemento.

## <a name="remarks"></a>Comentarios
 `TemplateID` es un elemento opcional.

 Si un archivo .vstemplate omite el `TemplateID` elemento, el [nombre](../extensibility/name-element-visual-studio-templates.md) elemento se usa como el identificador de la plantilla.

 El valor de la `TemplateID` elemento se usa junto con el registro del sistema de proyecto (HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\11.0\Projects\\) para filtrar plantillas que aparecen en la **Agregar nuevo elemento** cuadro de diálogo.

## <a name="see-also"></a>Vea también
- [Referencia de esquema de plantillas de Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
- [Crear plantillas para proyectos y elementos en Visual Studio](../ide/creating-project-and-item-templates.md)