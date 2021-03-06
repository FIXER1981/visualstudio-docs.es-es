---
title: Abrir y guardar elementos de proyecto | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], file persistence
- files [Visual Studio], opening and saving
- editors [Visual Studio SDK], file persistence
ms.assetid: f71898ad-335f-4c43-a177-4da87078afd1
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c406e66b1008f0bb2aad95a427e1329d4269f1f6
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68158069"
---
# <a name="opening-and-saving-project-items"></a>Apertura y guardado de elementos de proyecto
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Al agregar un nuevo tipo de proyecto, debe administrar la apertura y el guardado de los archivos de proyectos en el [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] entorno de desarrollo integrado (IDE). En los temas siguientes se describen los distintos enfoques para abrir y guardar archivos.  
  
## <a name="in-this-section"></a>En esta sección  
 [Visualización de archivos mediante el comando Abrir archivo](../../extensibility/internals/displaying-files-by-using-the-open-file-command.md)  
 Proporciona una explicación paso a paso de cómo el IDE controla el comando **Abrir archivo** y el rol de los proyectos de para responder a este comando.  
  
 [Visualización de archivos mediante el comando Abrir con](../../extensibility/internals/displaying-files-by-using-the-open-with-command.md)  
 Proporciona una explicación detallada y paso a paso de cómo el IDE controla el comando **Open with** , donde se solicita la apertura de un archivo que tiene algunas opciones de editores estándar.  
  
 [Apertura de editores específicos de proyecto](../../extensibility/how-to-open-project-specific-editors.md)  
 Proporciona instrucciones paso a paso para especificar que los archivos de un tipo determinado del proyecto se deben abrir con un editor específico del proyecto.  
  
 [Apertura de editores estándar](../../extensibility/how-to-open-standard-editors.md)  
 Proporciona instrucciones paso a paso para especificar cómo habilitar el IDE para abrir un editor estándar para los archivos del tipo de proyecto.  
  
 [Apertura de editores para documentos abiertos](../../extensibility/how-to-open-editors-for-open-documents.md)  
 Proporciona instrucciones paso a paso para abrir un editor específico del proyecto para un archivo abierto.  
  
 [Guardado de un documento estándar](../../extensibility/internals/saving-a-standard-document.md)  
 Proporciona una explicación detallada de cómo el IDE controla los comandos **Guardar**, **Guardar como**y **guardar todos los** comandos de un documento abierto en un editor estándar.  
  
 [Guardado de un documento personalizado](../../extensibility/internals/saving-a-custom-document.md)  
 Proporciona un diagrama y una explicación detallada de cómo el IDE controla el **guardado**, **Guardar como**y **guardar todos los** comandos para los documentos abiertos en un editor personalizado.  
  
 [Determinación del editor que abre un archivo en un proyecto](../../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md)  
 Describe el proceso que sigue el IDE para seleccionar el editor o el diseñador adecuado para un archivo.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Creación de diseñadores y editores personalizados](../../extensibility/creating-custom-editors-and-designers.md)  
 Enumera los cuatro tipos de editores que el IDE puede hospedar y proporciona descripciones de cada editor.  
  
 [Tipos de proyecto](../../extensibility/internals/project-types.md)  
 Describe cómo los proyectos controlan la forma en que se compila y se genera el código, cómo se abren los editores y cómo se da formato a los elementos del proyecto.
