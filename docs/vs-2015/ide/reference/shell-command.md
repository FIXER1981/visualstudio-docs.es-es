---
title: Comando Shell | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- tools.shell
helpviewer_keywords:
- exe files
- Shell command
- Tools.Shell command
- executables, running from Visual Studio
- .exe files
- Shell, launching exe files
- Visual Studio, executables from
ms.assetid: 737fda23-b852-45c4-a9fe-41cbce6ba70f
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: ad49aadf6be56fb330b883050e6a6ff893cf054a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "72663542"
---
# <a name="shell-command"></a>Shell (Comando)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Inicia programas ejecutables desde [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].

## <a name="syntax"></a>Sintaxis

```
Tools.Shell [/command] [/output] [/dir:folder] path [args]
```

## <a name="arguments"></a>Argumentos
 `path` Obligatorio. El nombre de archivo y la ruta de acceso del archivo que se va a ejecutar o el documento que se va a abrir. Se necesita una ruta de acceso completa si el archivo especificado no está en uno de los directorios de la variable de entorno PATH.

 `args` Opcional. Argumentos que se pasan al programa invocado.

## <a name="switches"></a>Modificadores
 /CommandWindow [o]/Command [o]/c [o]/cmd opcional. Especifica que la salida del ejecutable se muestra en la ventana **Comandos**.

 /dir: `folder` [o]/d: `folder` opcional. Especifica el directorio de trabajo que se establecerá cuando se ejecute el programa.

 /OutputWindow [o]/Output [o]/out [o]/o opcional. Especifica que la salida del ejecutable se muestra en la ventana **Salida**.

## <a name="remarks"></a>Observaciones
 Los modificadores /dir /o /c tienen que especificarse inmediatamente después de `Tools.Shell`. Cualquier elemento especificado después del nombre del ejecutable se pasa como argumentos de línea de comandos.

 El alias predefinido `Shell` se puede usar en lugar de `Tools.Shell`.

> [!CAUTION]
> Si el argumento `path` proporciona la ruta de acceso de directorio, así como el nombre de archivo, debe incluir la ruta de acceso completa entre comillas literales ("""), como en el siguiente ejemplo:

```
Tools.Shell """C:\Program Files\SomeFile.exe"""
```

 El procesador `Shell` interpreta cada conjunto de tres comillas dobles (""") como un único carácter de comilla doble. Por tanto, en el ejemplo anterior, se pasa la siguiente cadena de ruta de acceso al comando `Shell`:

```
"C:\Program Files\SomeFile.exe"
```

> [!CAUTION]
> Si no se coloca la cadena de ruta de acceso entre comillas literales ("""), Windows usará solo la parte de la cadena hasta el primer espacio. Por ejemplo, si la cadena de ruta de acceso anterior no se hubiera colocado correctamente entre comillas, Windows buscaría un archivo denominado "Program" que se encuentra en el directorio raíz C:\. Si un archivo ejecutable C:\Program.exe estuviera disponible, incluso uno instalado por una manipulación ilícita, Windows intentaría ejecutar ese programa en lugar del programa "C:\Archivos de programa\SomeFile.exe" deseado.

## <a name="example"></a>Ejemplo
 El siguiente comando usa xcopy.exe para copiar el archivo `MyText.txt` en la carpeta `Text`. La salida de xcopy.exe se muestra tanto en la **ventana Comandos** como en la ventana de **salida**.

```
>Tools.Shell /o /c xcopy.exe c:\MyText.txt c:\Text\MyText.txt
```

## <a name="see-also"></a>Consulte también
 [Ventana](../../ide/reference/command-window.md) de comandos de [comandos de Visual Studio](../../ide/reference/visual-studio-commands.md) [ventana de salida](../../ide/reference/output-window.md) alias de [comandos de Visual Studio](../../ide/reference/visual-studio-command-aliases.md) [cuadro Buscar/comando](../../ide/find-command-box.md)
