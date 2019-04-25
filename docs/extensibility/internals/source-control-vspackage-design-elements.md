---
title: Los elementos de diseño de VSPackage de Control de origen | Documentos de Microsoft
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control packages, design elements
ms.assetid: edd3f2ff-ca32-4465-8ace-4330493b67bb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9e10825bb9bc9659728fbaaeb023a595745b7bcd
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56642708"
---
# <a name="source-control-vspackage-design-elements"></a>Elementos de diseño de VSPackage de control de código fuente
Los temas de esta sección describen la estructura de VSPackage debe implementar para la integración profunda el control de código fuente. También se muestran las interfaces y que el VSPackage de control de origen de los servicios pueden implementar y las interfaces y los servicios puede usar el paquete VSPackage de control de código fuente de otros [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] componentes para admitir su origen de controlan la funcionalidad y modelo.

## <a name="in-this-section"></a>En esta sección
- [Estructura de VSPackage](../../extensibility/internals/vspackage-structure-source-control-vspackage.md)

 Define la estructura del VSPackage de control de origen.

- [Interfaces y servicios relacionados](../../extensibility/internals/related-services-and-interfaces-source-control-vspackage.md)

 Enumera las interfaces relacionadas con el paquete de control de origen y servicios.

- [Servicios proporcionados](../../extensibility/internals/services-provided-source-control-vspackage.md)

 Describe el servicio de control de código fuente proporcionado por el VSPackage de control de código fuente.

## <a name="related-sections"></a>Secciones relacionadas
- [Creación de un VSPackage de control de código fuente](../../extensibility/internals/creating-a-source-control-vspackage.md)

 Describe cómo crear un control de código fuente VSPackage que no solo proporciona la funcionalidad de control de código fuente, pero se puede usar para personalizar el [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] la interfaz de usuario de control de código fuente.