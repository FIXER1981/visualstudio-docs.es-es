---
title: Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Projects.VBDefaults
helpviewer_keywords:
- Option Explicit statement, setting in the IDE
- Option Compare statement, setting in the IDE
- Option Strict statement, setting in the IDE
ms.assetid: 2465cd9d-18b6-4c4a-b1ea-86dbab23fc79
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f33dd9b19297811597be406337d70392904e6e44
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/01/2020
ms.locfileid: "75596393"
---
# <a name="visual-basic-defaults-projects-options-dialog-box"></a>Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)
Especifica la configuración predeterminada de las opciones de proyecto de Visual Basic. Cuando se crea un proyecto, se agregarán las instrucciones de la opción especificada al encabezado del proyecto en el Editor de código. Las opciones se aplican a todos los proyectos de Visual Basic.

Para obtener acceso a este cuadro de diálogo, en el menú **Herramientas**, haga clic en **Opciones**, expanda la carpeta **Proyectos y soluciones** y después haga clic en **Valores predeterminados de VB**.

 **Option Explicit**

Establece el valor predeterminado del compilador para que las declaraciones explícitas de variables sean necesarias. De forma predeterminada, **Option Explicit** está establecido en **On**. Para más información, vea [/optionexplicit](/dotnet/visual-basic/reference/command-line-compiler/optionexplicit).

 **Option Strict**

Establece el valor predeterminado del compilador para que las conversiones de restricción explícitas sean necesarias y no se permita el enlace en tiempo de ejecución. De forma predeterminada, **Option Strict** está establecido en **Off**. Para más información, vea [/optionstrict](/dotnet/visual-basic/reference/command-line-compiler/optionstrict).

 **Option Compare**

Establece el valor predeterminado del compilador para las comparaciones de cadenas: binary (distingue mayúsculas de minúsculas) o text (no distingue mayúsculas de minúsculas). De forma predeterminada, **Option Compare** está establecido en **Binary**. Para más información, vea [/optioncompare](/dotnet/visual-basic/reference/command-line-compiler/optioncompare).

 **Option Infer**

Establece el valor predeterminado del compilador para la inferencia de tipo de variable local. De forma predeterminada, **Option Infer** está establecido en **On** para los proyectos recién creados y en **Off** para los proyectos migrados creados en versiones anteriores de Visual Basic. Para más información, vea [/optioninfer](/dotnet/visual-basic/reference/command-line-compiler/optioninfer).

## <a name="see-also"></a>Vea también

- [Soluciones y proyectos](../../ide/solutions-and-projects-in-visual-studio.md)
