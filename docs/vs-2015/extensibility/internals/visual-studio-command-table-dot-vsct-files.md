---
title: Tabla de comandos de Visual Studio (. Archivos Vsct) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, overview
- Visual Studio command table configuration files (VSCT), overview
ms.assetid: 1313adb4-add4-4e74-90e2-f4be522f5259
caps.latest.revision: 23
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 98b3892d10b003d6236ae9ccfbebb83a602a5877
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "58987696"
---
# <a name="visual-studio-command-table-vsct-files"></a>Archivos de tabla de comandos de Visual Studio (.Vsct)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Un archivo de configuración de la tabla de comandos es un archivo de texto que describe el conjunto de comandos que contiene un paquete VSPackage. El [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] comando de compilador de tabla (VSCT) compila los archivos de configuración basado en XML (archivos .vsct) en archivos de salida (.cto) de tabla de comando binary. Los archivos .cto resultante son los mismos que los que se crean mediante el compilador de tabla (CTC) del comando para compilar los archivos de configuración de CTC. Sin embargo, los archivos .vsct basado en XML tiene algunas ventajas, como un editor XML y XML IntelliSense.  
  
 Para obtener más información sobre la sintaxis y semántica de los archivos .vsct, vea [diseño de tabla de comandos XML (. Archivos Vsct)](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
  
## <a name="in-this-section"></a>En esta sección  
 [Diseño de archivos de tabla de comandos XML (.Vsct)](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
 Describe cómo diseñar .vsct (archivos).  
  
 [Cómo: Crear una. Archivo de Vsct](../../extensibility/internals/how-to-create-a-dot-vsct-file.md)  
 Compara los métodos para crear un archivo .vsct. Describe el proceso para crear manualmente un nuevo archivo de vsct.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Referencia del esquema XML de VSCT](../../extensibility/vsct-xml-schema-reference.md)  
 Proporciona detalles sobre cada sección del archivo de configuración XML de tabla de comandos.  
  
 [Configuración de la tabla de comandos (. Archivos de CTC)](http://msdn.microsoft.com/3413dda1-f372-4669-bcf0-c64d3463842c)  
 Presenta información general sobre el formato de archivo .ctc en desuso.  
  
 [Adición de elementos de la interfaz de usuario por VSPackages](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)  
 Describe la especificación de formato de tabla de comandos.  
  
 [Recursos de VSPackages](../../extensibility/internals/resources-in-vspackages.md)  
 Describe cómo usar los recursos administrados y en los paquetes VSPackage administrados.  
  
 [Comandos, menús y barras de herramientas](../../extensibility/internals/commands-menus-and-toolbars.md)  
 Explica cómo crear una interfaz de usuario que incluya menús, barras de herramientas y cuadros combinados de comandos.
