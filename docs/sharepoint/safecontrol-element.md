---
title: SafeControl (elemento) | Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SafeControl element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e6b47254a80c9cdadab6ca18f2fb8c3e8540fbd0
ms.sourcegitcommit: 3d37c2460584f6c61769be70ef29c1a67397cf14
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2019
ms.locfileid: "58324570"
---
# <a name="safecontrol-element"></a>SafeControl (elemento)
  Representa un control ASPX o elemento Web que se designa como seguro para que cualquier usuario tenga acceso en cualquier página ASPX del sitio de SharePoint.

## <a name="syntax"></a>Sintaxis

```xml
<SafeControl Assembly = "Name of assembly that contains the safe control"
    IsSafe = "true/false"
    IsSafeAgainstScript = "true/false"
    Name = "Name of this safe control entry"
    Namespace = "Namespace of the safe control"
    TypeName = "Type of the safe control" />
```

## <a name="attributes-and-elements"></a>Atributos y elementos
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|**Ensamblado**|Opcional **xs: String** atributo.<br /><br /> El nombre del ensamblado donde se define el control ASPX o elemento Web. De forma predeterminada, este atributo se usa el **$SharePoint.Project.AssemblyFullName$** parámetro reemplazable para el nombre del ensamblado. Para obtener más información, consulte [parámetros reemplazables](../sharepoint/replaceable-parameters.md).|
|**IsSafe**|Opcional **xs: Boolean** atributo.<br /><br /> Especifica si el control ASPX o elemento Web es seguro para los usuarios de confianza tener acceso a.|
|**IsSafeAgainstScript**|Opcional **xs: Boolean** atributo.<br /><br /> Especifica si los usuarios de confianza pueden ver o editar las propiedades del control ASPX o elemento Web.|
|**Name**|Opcional **xs: String** atributo.<br /><br /> El nombre de esta entrada de control segura en la colección.|
|**Espacio de nombres**|Opcional **xs: String** atributo.<br /><br /> El espacio de nombres del control ASPX o elemento Web.|
|**TypeName**|Opcional **xs: String** atributo.<br /><br /> El nombre de tipo del control ASPX o elemento Web.|

### <a name="child-elements"></a>Elementos secundarios
 Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|[SafeControls](../sharepoint/safecontrols-element.md)|Representa una colección de controles ASPX y elementos Web que se designan como seguros para cualquier usuario tenga acceso en cualquier página ASPX del sitio de SharePoint.|

## <a name="remarks"></a>Comentarios
 Para obtener más información sobre los controles seguros, vea [proporcionar información de empaquetado e implementación de elementos de proyecto](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).

## <a name="element-information"></a>Información de elemento

|||
|-|-|
|**Espacio de nombres**|http:\/\/schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|
|**Nombre de esquema**|Esquema de elemento de proyecto de SharePoint|
|**Archivo de validación**|ProjectItemModelSchema.xsd|
|**Puede estar vacío**|No|

## <a name="see-also"></a>Vea también
- [Referencia de esquemas de elemento de proyecto de SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)
- [Proporcionar información de empaquetado e implementación de elementos de proyecto](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)
