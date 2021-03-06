---
title: Arquitectura de tipos de proyecto | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], architecture
ms.assetid: 9c1d940f-8a54-41f7-a8aa-c870e324371c
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e53929b1ec2ed9c73191bf16f1cedc84a53b58f2
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80706320"
---
# <a name="project-types-architecture"></a>Arquitectura de tipos de proyecto
En esta sección se incluye información detallada sobre la arquitectura de los tipos de proyecto en [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] .

## <a name="in-this-section"></a>En esta sección
- [Elementos de un modelo de proyecto](../../extensibility/internals/elements-of-a-project-model.md)

 Enumera los servicios que un tipo de proyecto puede consumir y las interfaces que debe implementar.

- [Componentes principales del modelo de proyecto](../../extensibility/internals/project-model-core-components.md)

 Describe los tipos de proyecto de interfaces que deben implementar y, opcionalmente, pueden implementar para proporcionar funcionalidad adicional.

- [Momento para la creación de tipos de proyecto](../../extensibility/internals/when-to-create-project-types.md)

 Ayuda a decidir cuándo debe crear un tipo de proyecto y cuándo puede usar otra [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] característica de extensibilidad como VSPackages y editores para lograr el mismo objetivo.

- [Jerarquías y selección](../../extensibility/internals/hierarchies-and-selection.md)

 Describe cómo [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] utiliza jerarquías y el contexto de selección para proporcionar una experiencia de usuario coherente y simplificada.

## <a name="related-sections"></a>Secciones relacionadas
- [Subtipos de proyecto](../../extensibility/internals/project-subtypes.md)

 Explica cómo los subtipos de proyecto permiten personalizar el comportamiento de los sistemas de proyectos de [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] y [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] .

- [Tipos de proyecto](../../extensibility/internals/project-types.md)

 Proporciona información general sobre los proyectos como los bloques de creación básicos del [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] entorno de desarrollo integrado (IDE). Se proporcionan vínculos a temas adicionales que explican cómo los proyectos controlan la compilación y compilación de código.
