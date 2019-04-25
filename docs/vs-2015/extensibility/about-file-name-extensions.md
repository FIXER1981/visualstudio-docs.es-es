---
title: Acerca de las extensiones de nombre de archivo | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- file extensions
- file name extensions
ms.assetid: 99f4f9ff-fb84-4258-9787-6890f308a57f
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 866a30279ca2c79f4a490a040f76bc3a86c6a6e1
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "58987606"
---
# <a name="about-file-name-extensions"></a>Acerca de las extensiones de nombre de archivo
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Al registrar una extensión de archivo de un paquete VSPackage, asocia con una versión de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Esto es importante si más de una versión de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] está instalado en un equipo.  
  
 Extensiones de archivo para paquetes VSPackage registradas bajo la clave HKEY_CLASSES_ROOT con un valor predeterminado que señala el identificador de programación (ProgID) asociado.  
  
 Este es un ejemplo de la información de registro para la extensión de archivo .vcproj:  
  
```  
HKEY_CLASSES_ROOT\  
   .vcproj\  
      (default)=" VisualStudio.vcproj.8.0"   
```  
  
 Los archivos asociados con [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] deben tener un ProgID con control de versiones, como `VisualStudio.vcproj.8.0`, para permitir que las instalaciones en paralelo del producto para mantener las asociaciones de extensión de archivo entre las versiones de producto. Un ProgID específico de la versión también permite usar los verbos estándar, como abrir, editar y así sucesivamente, sin preocuparse de sobrescribir ni ser sobrescrito por otras aplicaciones o las versiones de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
 En algunos casos, no se debe cambiar el identificador de programa asociado con una extensión de archivo. Por ejemplo, el ProgID de la extensión de archivo .htm (progid = archivo HTML) está codificado en varios lugares en el sistema operativo, y es muy conocida y se usa en asociación con archivos .htm y .html.  
  
## <a name="see-also"></a>Vea también  
 [Registrar las extensiones de nombre de archivo para las implementaciones en paralelo](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)   
 [Especificación de controladores de archivo para extensiones de nombre de archivo](../extensibility/specifying-file-handlers-for-file-name-extensions.md)
