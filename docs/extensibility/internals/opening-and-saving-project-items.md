---
title: Abrir y guardar elementos de proyecto | Documentos de Microsoft
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], file persistence
- files [Visual Studio], opening and saving
- editors [Visual Studio SDK], file persistence
ms.assetid: f71898ad-335f-4c43-a177-4da87078afd1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7ca83cb6d2913e0c0a91f4a6e874640ae57c7708
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56602434"
---
# <a name="opening-and-saving-project-items"></a>Apertura y guardado de elementos de proyecto
Cuando se agrega un nuevo tipo de proyecto, debe administrar la apertura y el almacenamiento de los archivos de proyectos en el [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] el entorno de desarrollo integrado (IDE). Los temas siguientes describen los diferentes enfoques para abrir y guardar archivos.

## <a name="in-this-section"></a>En esta sección
- [Visualización de archivos mediante el comando Abrir archivo](../../extensibility/internals/displaying-files-by-using-the-open-file-command.md)

 Proporciona una explicación paso a paso de cómo el IDE controla la **abrir archivo** comando y el rol de los proyectos de responder a este comando.

- [Visualización de archivos mediante el comando Abrir con](../../extensibility/internals/displaying-files-by-using-the-open-with-command.md)

 Proporciona una explicación detallada, paso a paso de cómo el IDE controla la **abrir con** comando, solicitar la apertura de un archivo que tiene algunas opciones de editores estándar.

- [Cómo: Abrir editores específicos del proyecto](../../extensibility/how-to-open-project-specific-editors.md)

 Proporciona instrucciones paso a paso para especificar que los archivos de un tipo determinado en el proyecto deben abrirse con un editor específico del proyecto.

- [Cómo: Abrir editores estándar](../../extensibility/how-to-open-standard-editors.md)

 Proporciona instrucciones paso a paso para especificar cómo se habilita el IDE abrir un editor estándar para los archivos en el tipo de proyecto.

- [Cómo: Abrir editores para documentos abiertos](../../extensibility/how-to-open-editors-for-open-documents.md)

 Proporciona instrucciones paso a paso para abrir un editor específico del proyecto para un archivo abierto.

- [Guardado de un documento estándar](../../extensibility/internals/saving-a-standard-document.md)

 Proporciona una explicación detallada de cómo el IDE controla la **guardar**, **Guardar como**, y **guardar todo** comandos para un documento abierto en un editor estándar.

- [Guardado de un documento personalizado](../../extensibility/internals/saving-a-custom-document.md)

 Proporciona un diagrama y una explicación detallada de cómo el IDE controla la **guardar**, **Guardar como**, y **guardar todo** comandos para los documentos abiertos en un editor personalizado.

- [Determinación del editor que abre un archivo en un proyecto](../../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md)

 Explica el proceso que sigue el IDE para seleccionar el editor adecuado o el diseñador para un archivo.

## <a name="related-sections"></a>Secciones relacionadas
- [Creación de diseñadores y editores personalizados](../../extensibility/creating-custom-editors-and-designers.md)

 Enumera los cuatro tipos de editores que el IDE puede hospedar y ofrece una descripción de cada editor.

- [Tipos de proyecto](../../extensibility/internals/project-types.md)

 Describe cómo los proyectos de controlan la manera en que el código se compila y se compila, cómo se abren los editores y cómo se da formato a los elementos de proyecto.