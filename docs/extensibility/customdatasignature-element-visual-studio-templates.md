---
title: CustomDataSignature (elemento) (plantillas de Visual Studio) | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- <CustomDataSignature> Element (Visual Studio Templates)
- CustomDataSignature Element (Visual Studio Templates)
ms.assetid: 8c3db51d-7014-4484-802a-15aa1353dbdb
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: db2b4d089495245d1a37469df1dc43a19be31866
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "66351977"
---
# <a name="customdatasignature-element-visual-studio-templates"></a>CustomDataSignature (elemento) (plantillas de Visual Studio)
Especifica la firma de texto para buscar los datos personalizados.

 \<VSTemplate> \<TemplateData> \<CustomDataSignature>

## <a name="syntax"></a>Sintaxis

```
<CustomDataSignature>"string"</CustomDataSignature>
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Elemento necesario.<br /><br /> Clasifica la plantilla y define cómo se muestran en el el **nuevo proyecto** o **Agregar nuevo elemento** cuadro de diálogo.|

## <a name="text-value"></a>Valor de texto
 Se requiere un valor de texto.

 El texto es una cadena que tiene la firma de texto que se necesita para localizar los datos personalizados.

## <a name="remarks"></a>Comentarios
 `CustomDataSignature` es un elemento opcional.

## <a name="see-also"></a>Vea también
- [Referencia de esquema de Visual Studio plantilla](../extensibility/visual-studio-template-schema-reference.md)
- [Crear plantillas para proyectos y elementos](../ide/creating-project-and-item-templates.md)