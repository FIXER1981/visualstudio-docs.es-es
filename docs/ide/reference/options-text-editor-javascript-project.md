---
title: Opciones, Editor de texto, JavaScript, Proyecto
ms.date: 1/15/2019
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Project.General
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Project
- VS.ToolsOptionsPages.Text_Editor.TypeScript.Project.General
- VS.ToolsOptionsPages.Text_Editor.TypeScript.Project
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 09ed64d6bffaa4453c3294229ee48fd0a065eb74
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62778178"
---
# <a name="options-text-editor-javascript-project"></a>Opciones, Editor de texto, JavaScript, Proyecto

Use la página **Proyecto** del cuadro de diálogo **Opciones** para especificar las opciones de proyecto de JavaScript en el Editor de código. Para acceder a esta página, en la barra de menús elija **Herramientas** > **Opciones** y expanda **Editor de texto** > **JavaScript** > **Proyecto**.

## <a name="project-analysis-options"></a>Opciones de análisis del proyecto

Estas opciones determinan cómo el editor analiza proyectos, informa diagnósticos y sugiere mejoras. Active o desactive las opciones para especificar cómo el editor va a administrar estas situaciones.

### <a name="uielement-list"></a>Lista de UIElement

- **Analizar solo los proyectos que contienen archivos abiertos en el editor**
- **Notificar solo el diagnóstico de los archivos abiertos en el editor**
- **Sugerir posibles mejoras que no son correcciones**

## <a name="virtual-projects-in-solution-explorer"></a>Proyectos virtuales en el Explorador de soluciones

Estas opciones le permiten elegir si mostrar los proyectos virtuales cuando una solución se carga o no se carga.

## <a name="compile-on-save"></a>Compilar al guardar

Estas opciones determinan si los archivos TypeScript que no forman parte del proyecto se compilan automáticamente. Active la casilla de verificación y elija el tipo de generación de código que se va a usar.

### <a name="uielement-list"></a>Lista de UIElement

- **Usar la generación de código AMD para los módulos que no forman parte de un proyecto**
- **Usar la generación de código CommonJS para los módulos que no forman parte de un proyecto**
- **Usar la generación de código UMD para los módulos que no forman parte de un proyecto**
- **Usar la generación de código del sistema para los módulos que no forman parte de un proyecto**
- **Usar la generación de código ES2015 para los módulos que no forman parte de un proyecto**

## <a name="ecmascript-version-for-files-that-are-not-part-of-a-project"></a>Versión de ECMAScript para los archivos que no forman parte de un proyecto

Estas opciones le permiten seleccionar la versión de ECMAScript para los archivos que no forman parte de un proyecto. Puede elegir entre **ECMAScript 3**, **ECMAScript 5** o **ECMAScript 6**.

## <a name="jsx-emit-for-tsx-files-that-are-not-part-of-a-project"></a>Emisión de JSX para los archivos TSX que no forman parte de un proyecto

Estas opciones determinan cómo el editor trata los archivos TypeScript que no forman parte de un proyecto.

### <a name="uielement-list"></a>Lista de UIElement

|Opción|Descripción|
|------------|-----------------|
|**React Framework**|Cuando se selecciona esta opción, el Editor de código emite una extensión de archivo *.js*.|
|**Preserve**|Cuando se selecciona esta opción, el Editor de código mantiene el archivo JSX como parte de la salida y emite una extensión de archivo *.jsx*.|

## <a name="see-also"></a>Vea también

- [General, Entorno, Opciones (Cuadro de diálogo)](../../ide/reference/general-environment-options-dialog-box.md)