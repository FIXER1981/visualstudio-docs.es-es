---
title: Nuevo archivo (Comando)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- file.newfile
helpviewer_keywords:
- File.NewFile command
- New File command
ms.assetid: 767868d6-a525-425b-a43b-2198f636ab6b
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5fe8a99ee59a347fdcb7cff601b75139760630f7
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "75595961"
---
# <a name="new-file-command"></a>Nuevo archivo (Comando)
Crea un archivo y lo abre. El archivo aparece en la carpeta Archivos varios.

## <a name="syntax"></a>Sintaxis

```cmd
File.NewFile [filename] [/t:templatename] [/editor:editorname]
```

## <a name="arguments"></a>Argumentos
`filename`

Opcional. Nombre para el archivo. Si no se proporciona ningún nombre, se asigna un nombre predeterminado. Si no se muestra ningún nombre de plantilla, se crea un archivo de texto.

## <a name="switches"></a>Modificadores
/t:`templatename`\
Opcional. Especifica el tipo de archivo que se va a crear.

La sintaxis del argumento /t:`templatename` refleja la información que se encuentra en el cuadro de diálogo Nuevo archivo. Escriba el nombre de categoría seguido de una barra diagonal inversa (`\`) y el nombre de plantilla, e incluya toda la cadena entre comillas.

Por ejemplo, para crear un archivo de código fuente de [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)], tiene que escribir lo siguiente para el argumento /t:`templatename`.

```cmd
/t:"Visual C++\C++ File (.cpp)"
```

En el ejemplo anterior se indica que la plantilla de archivo de C++ se encuentra en la categoría de Visual C++ del cuadro de diálogo **Nuevo archivo**.

/e:`editorname`\
Opcional. Nombre del editor en el que se abrirá el archivo. Si se especifica el argumento pero no se ha proporcionado ningún nombre de editor, aparece el cuadro de diálogo **Abrir con**.

La sintaxis del argumento /e:`editorname` usa los nombres de editor tal y como aparecen en el cuadro de diálogo Abrir con, incluidos entre comillas.

Por ejemplo, para abrir un archivo en el editor de código fuente, tiene que escribir lo siguiente para el argumento /e:`editorname`.

```cmd
/e:"Source Code (text) Editor"
```

## <a name="example"></a>Ejemplo
En este ejemplo se crea la página web "test1.htm" y se abre en el editor de código fuente.

```cmd
>File.NewFile test1 /t:"General\HTML Page" /e:"Source Code (text) Editor"
```

## <a name="see-also"></a>Vea también

- [Comandos de Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Ventana Comandos](../../ide/reference/command-window.md)
- [Ventana Inmediato](../../ide/reference/immediate-window.md)
- [Cuadro Buscar/Comando](../../ide/find-command-box.md)
- [Alias de comandos de Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
