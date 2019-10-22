---
title: Comando Nuevo archivo | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- file.newfile
helpviewer_keywords:
- File.NewFile command
- New File command
ms.assetid: 767868d6-a525-425b-a43b-2198f636ab6b
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 8e0d25d585f518c854ad6176ae4ae7a5f27b22ad
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2019
ms.locfileid: "72671958"
---
# <a name="new-file-command"></a>Nuevo archivo (Comando)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Crea un archivo y lo abre. El archivo aparece en la carpeta Archivos varios.

## <a name="syntax"></a>Sintaxis

```
File.NewFile [filename] [/t:templatename] [/editor:editorname]
```

## <a name="arguments"></a>Argumentos
 `filename` Opcional. Nombre para el archivo. Si no se proporciona ningún nombre, se asigna un nombre predeterminado. Si no se muestra ningún nombre de plantilla, se crea un archivo de texto.

## <a name="switches"></a>Modificadores
 /t:`templatename` opcional. Especifica el tipo de archivo que se va a crear.

 La sintaxis del argumento /t:`templatename` refleja la información que se encuentra en el cuadro de diálogo Nuevo archivo. Escriba el nombre de categoría seguido de una barra diagonal inversa (`\`) y el nombre de plantilla, e incluya toda la cadena entre comillas.

 Por ejemplo, para crear un archivo de código fuente de [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)], tiene que escribir lo siguiente para el argumento /t:`templatename`.

```
/t:"Visual C++\C++ File (.cpp)"
```

 En el ejemplo anterior se indica que la plantilla de archivo de C++ se encuentra en la categoría de Visual C++ del cuadro de diálogo **Nuevo archivo**.

 /e:`editorname` opcional. Nombre del editor en el que se abrirá el archivo. Si se especifica el argumento pero no se ha proporcionado ningún nombre de editor, aparece el cuadro de diálogo **Abrir con**.

 La sintaxis del argumento /e:`editorname` usa los nombres de editor tal y como aparecen en el cuadro de diálogo Abrir con, incluidos entre comillas.

 Por ejemplo, para abrir un archivo en el editor de código fuente, tiene que escribir lo siguiente para el argumento /e:`editorname`.

```
/e:"Source Code (text) Editor"
```

## <a name="example"></a>Ejemplo
 En este ejemplo se crea la página web "test1.htm" y se abre en el editor de código fuente.

```
>File.NewFile test1 /t:"General\HTML Page" /e:"Source Code (text) Editor"
```

## <a name="see-also"></a>Otras referencias
 [Comandos de Visual Studio](../../ide/reference/visual-studio-commands.md) [ventana comandos](../../ide/reference/command-window.md) [inmediato ventana](../../ide/reference/immediate-window.md) [Buscar/comando cuadro](../../ide/find-command-box.md) de comandos [Visual Studio alias de comandos](../../ide/reference/visual-studio-command-aliases.md)
