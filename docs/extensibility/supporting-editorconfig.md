---
title: Ampliación de un servicio de lenguaje para admitir EditorConfig en Visual Studio | Documentos de Microsoft
ms.date: 11/22/2017
ms.topic: conceptual
helpviewer_keywords:
- editorconfig [extensibility]
- editorconfig, supporting in a language service
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3c29c22ae4539d874ffc08c9ce5adf94ab33d404
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56696979"
---
# <a name="supporting-editorconfig-for-your-language-service"></a>Compatibilidad con EditorConfig el servicio de lenguaje

[EditorConfig](http://editorconfig.org/) archivos le permiten describir opciones comunes de editor de texto, como el tamaño de sangría, en cada proyecto. Para obtener más información sobre la compatibilidad de Visual Studio para los archivos EditorConfig, vea [crear configuración de editor y portátiles con EditorConfig](../ide/create-portable-custom-editor-options.md).

En la mayoría de los casos, cuando se implementa un servicio de lenguaje de Visual Studio, no es necesario llevar a cabo ninguna tarea adicional para admitir las propiedades universales de EditorConfig. El editor principal detecta automáticamente y lee el archivo .editorconfig cuando los usuarios abren archivos, y establece el búfer de texto y las opciones de visualización adecuados. Sin embargo, para las ediciones, como tabulaciones y espacios, algunos servicios de lenguaje optar por usar una opción de vista de texto contextual adecuada en lugar de usar la configuración global. En estos casos, el servicio de lenguaje debe actualizarse para que admita archivos EditorConfig.

Estos son los cambios que son necesarios para actualizar un servicio de lenguaje para admitir los archivos EditorConfig, reemplazando una global _específico del lenguaje_ opción con un _contextuales_ opción:

## <a name="indent-style"></a>Estilo de sangría

Opciones específicas del idioma | Opciones contextuales
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.fInsertTabs<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs|!textBufferOptions.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)<br/>!textView.Options.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)

## <a name="indent-size"></a>Tamaño de sangría

Opciones específicas del idioma | Opciones contextuales
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uIndentSize<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.IndentSize|textBufferOptions.GetOptionValue(DefaultOptions.IndentSizeOptionId)<br/>textView.Options.GetOptionValue(DefaultOptions.IndentSizeOptionId)

## <a name="tab-size"></a>Tamaño de tabulación

Opciones específicas del idioma | Opciones contextuales
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uTabSize<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.TabSize|textBufferOptions.GetOptionValue(DefaultOptions.TabSizeOptionId)<br/>textView.Options.GetOptionValue(DefaultOptions.TabSizeOptionId)

## <a name="see-also"></a>Vea también

- [Crear una configuración de editor y portátiles con EditorConfig](../ide/create-portable-custom-editor-options.md)
- [Ampliar los servicios de editor y lenguaje](../extensibility/extending-the-editor-and-language-services.md)