---
title: Interfaces heredadas en el editor | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy
ms.assetid: 741d45f5-0ea3-4614-972a-8728fe054e07
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 8483068ae03c9a57fc67b528393e5d6830c3ec33
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68180290"
---
# <a name="legacy-interfaces-in-the-editor"></a>Interfaces heredadas en el editor
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Puede tener acceso al editor de Visual Studio desde interfaces heredadas. El SDK de Visual Studio incluye adaptadores conocidos como *correcciones de compatibilidad (Shim*), que permiten a estas interfaces interactuar con el nuevo editor. No obstante, se recomienda actualizar el código heredado para usar la nueva API del editor. El código funcionará mejor y podrá usar nuevas tecnologías, como el Windows Presentation Foundation (WPF) y el Managed Extensibility Framework (MEF).  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Title|Descripción|  
|-----------|-----------------|  
|[Adaptación del código heredado en el editor](../extensibility/adapting-legacy-code-to-the-editor.md)|Explica cómo adaptar el código al nuevo editor.|  
|[Comportamiento nuevo o modificado con los adaptadores del editor](../extensibility/new-or-changed-behavior-with-editor-adapters.md)|Explica cómo el comportamiento de los adaptadores del editor difiere del de las versiones anteriores del editor.|  
|[Dentro del editor principal](../extensibility/inside-the-core-editor.md)|Describe los diferentes componentes de versiones anteriores del editor.|  
|[Creación de instancias del editor principal mediante la API heredada](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)|Explica cómo usar la API heredada para crear una instancia del editor principal.|  
|[Generadores del editor](../extensibility/editor-factories.md)|Explica cómo usar los generadores de editores con la API heredada.|  
|[Cómo: Registrar tipos de archivo del editor](../extensibility/how-to-register-editor-file-types.md)|Explica cómo vincular una extensión de nombre de archivo al editor.|  
|[Tutorial: Crear un editor principal y registrar un tipo de archivo del editor](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)|Explica cómo crear un editor básico y vincularle una extensión de nombre de archivo.|  
|[Cómo: Proporcionar el contexto para los editores](../extensibility/how-to-provide-context-for-editors.md)|Explica cómo proporcionar el contexto para el editor.|  
|[Servicios de lenguaje y editor principal](../extensibility/language-services-and-the-core-editor.md)|Explica las interacciones entre un servicio de lenguaje y un editor.|  
|[Acceso al búfer de texto mediante la API heredada](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)|Explica cómo obtener acceso al búfer de texto mediante la API heredada.|  
|[Acceso a la vista de texto mediante la API heredada](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)|Explica cómo obtener acceso a la vista de texto mediante la API heredada.|  
|[Personalización de las ventanas de código mediante la API heredada](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)|Explica cómo personalizar las ventanas de código mediante la API heredada.|  
|[Acceso a las capas de texto mediante la API heredada](../extensibility/accessing-text-layers-by-using-the-legacy-api.md)|Explica cómo obtener acceso a diferentes capas de texto mediante la API heredada.|  
|[Uso de marcadores de texto con la API heredada](../extensibility/using-text-markers-with-the-legacy-api.md)|Explica cómo agregar marcadores de texto mediante la API heredada.|  
|[Personalización de los controles y los menús del editor mediante la API heredada](../extensibility/customizing-editor-controls-and-menus-by-using-the-legacy-api.md)|Explica cómo personalizar los controles de editor mediante la API heredada.|  
|[Administración de las fases de reversión y puesta al día mediante la API heredada](../extensibility/managing-undo-and-redo-by-using-the-legacy-api.md)|Explica cómo administrar las acciones de deshacer y rehacer mediante la API heredada.|  
|[Cómo: Implementar el mecanismo Buscar y reemplazar](../extensibility/how-to-implement-the-find-and-replace-mechanism.md)|Explica cómo administrar buscar y reemplazar mediante la API heredada.|  
|[Cómo: Suprimir las notificaciones de cambios de archivos](../extensibility/how-to-suppress-file-change-notifications.md)|Explica cómo suprimir las notificaciones de cambio de archivo mediante la API heredada.|  
|[Creación de diseñadores y editores personalizados](../extensibility/creating-custom-editors-and-designers.md)|Explica cómo crear editores y diseñadores personalizados.|  
|[Desarrollo de un servicio de lenguaje heredado](../extensibility/internals/developing-a-legacy-language-service.md)|Proporciona vínculos a documentos sobre características que proporcionan funciones de personalización al [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] editor principal agregando compatibilidad para un servicio de lenguaje.|  
|[Uso de fuentes y colores](../extensibility/using-fonts-and-colors.md)|Explica cómo usar fuentes y colores con interfaces heredadas.|
