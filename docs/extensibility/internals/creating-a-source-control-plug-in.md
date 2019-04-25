---
title: Creación de un Control de código fuente complemento | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- plug-ins, source control
- source control plug-ins
- source control [Visual Studio SDK], plug-ins
ms.assetid: c7e69fa4-150e-469a-a6fc-fa1260bdbb07
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c33b852a585825f3c5b5fc415b01ac31e35f763f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56606539"
---
# <a name="create-a-source-control-plug-in"></a>Crear un control de código fuente complemento
El SDK de Visual Studio proporciona los recursos que le permiten agregar funcionalidad de control de código fuente para el [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] el entorno de desarrollo integrado (IDE). Le permite usar cualquier DLL del complemento que cumple con la API de complemento de Control de origen que se describen en esta documentación.

## <a name="in-this-section"></a>En esta sección
- [Introducción](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)

 Describe cómo instalar un complemento de control de origen y resalta las versiones de API de complemento de Control de código fuente está disponibles.

- [Arquitectura](../../extensibility/internals/source-control-plug-in-architecture.md)

 Se usa un diagrama de arquitectura para explicar la integración de un control de código fuente con el [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.

- [Guía de prueba](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)

 Se proporcionan instrucciones sobre cómo probar la instalación y el funcionamiento de un complemento de control de código fuente.

## <a name="related-sections"></a>Secciones relacionadas
- [Crear un VSPackage de control de código fuente](../../extensibility/internals/creating-a-source-control-vspackage.md)

 Describe cómo crear un control de código fuente VSPackage que proporciona funcionalidad de control de código fuente pero que no sólo reemplaza [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] la interfaz de usuario de control de código fuente.

- [Complementos de control de código fuente](../../extensibility/source-control-plug-ins.md)

 Proporciona una lista completa de todos los elementos de la API de complemento de Control de código fuente.

- [Control de código fuente](../../extensibility/internals/source-control.md)

 Describe las opciones para implementar el control de código fuente como una característica integrada de [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].
