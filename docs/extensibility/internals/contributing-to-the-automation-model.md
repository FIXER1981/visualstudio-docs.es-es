---
title: Contribuir al modelo de automatización | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK]
ms.assetid: 44de482d-93c8-41a4-843c-cefda995a03e
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d660edc740229c3e91b99e1f59eb37b4e9312098
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80709266"
---
# <a name="contribute-to-the-automation-model"></a>Contribuir al modelo de automatización
Visual Studio proporciona un conjunto de interfaces de automatización para personalizar el entorno. El modelo de automatización es el modelo de objetos que permite a los usuarios finales crear extensiones y complementos de Visual Studio.

 Además, es adecuado para usted, como desarrollador de VSPackage, contribuir al modelo de automatización; al hacerlo, habilita a los usuarios finales de su VSPackage para crear complementos y, por lo general, proporcionan una experiencia de modelo de usuario coherente cuando usan el VSPackage en [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] .

 Para que la experiencia del usuario final sea coherente, puede seguir un conjunto de instrucciones mientras diseña el VSPackage para que el modelo de automatización del VSPackage siga las ideas de [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] .

## <a name="in-this-section"></a>En esta sección
- [Información general del modelo de automatización](../../extensibility/internals/automation-model-overview.md)

 Define el modelo de automatización como grupos de objetos relacionados que controlan las principales caras del entorno común. Este conjunto de objetos se imagen en un diagrama del modelo de automatización.

- [Proporcionar automatización para VSPackages](../../extensibility/internals/providing-automation-for-vspackages.md)

 Describe las dos maneras principales de proporcionar automatización para el VSPackage.

- [Exponer objetos de proyecto](../../extensibility/internals/exposing-project-objects.md)

 Proporciona instrucciones paso a paso para crear objetos específicos de VSPackage.

- [Modelado de proyectos](../../extensibility/internals/project-modeling.md)

 Explica los objetos de proyecto estándar necesarios para crear la automatización para el nuevo tipo de proyecto e ilustra la ruta de acceso que sigue la automatización del proyecto. En este tema también se proporcionan listas de declaraciones e implementación de clases.

- [Exponer eventos](../../extensibility/internals/exposing-events-in-the-visual-studio-sdk.md)

 Proporciona instrucciones paso a paso para crear eventos para el modelo de automatización.

- [Compatibilidad de automatización con las páginas de opciones](../../extensibility/internals/automation-support-for-options-pages.md)

 Describe cómo devolver un objeto de automatización para admitir las propiedades del cuadro de diálogo **Opciones** personalizadas de un VSPackage en el menú de **herramientas** extendiendo el `DTE.Properties` objeto.

- [Proporcionar automatización para el código](../../extensibility/internals/providing-automation-for-code.md)

 Explica que no es necesario crear un modelo de automatización para el código. Sin embargo, en este tema se proporciona un vínculo que proporciona información detallada sobre los modelos de código.

- [Cómo: proporcionar automatización para Windows](../../extensibility/internals/how-to-provide-automation-for-windows.md)

 Explica que proporcionar automatización es una buena idea siempre que desee que los objetos de automatización estén disponibles en una ventana de y el entorno no proporcione un objeto de automatización listo para usar. Describe la automatización para las ventanas de herramientas y de documento.

- [Usar el modelo de automatización](../../extensibility/internals/using-the-automation-model.md)

 Proporciona dos ejemplos de código que muestran cómo un consumidor de automatización obtiene los objetos de automatización de proyecto iniciales.

- [Automatización para objetos Configuration y SelectedItem](../../extensibility/internals/automation-for-configuration-and-selecteditem-objects.md)

 Proporciona información sobre la automatización de los objetos Configuration y SelectedItems.

## <a name="reference"></a>Referencia
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> Proporciona un ejemplo de código que muestra cómo un VSPackage participa en el modelo de objetos de automatización DTE. Muestra los parámetros, los valores devueltos y los comentarios seleccionados.
