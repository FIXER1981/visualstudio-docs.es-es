---
title: Ruta de acceso de símbolos (Comando)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- debug.symbolpath
helpviewer_keywords:
- symbol path command
- Debug.SymbolPath command
- SymbolPath command
ms.assetid: b697ef2d-3f5d-40df-b113-7068a5bec0d4
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ed8ec8e7f990a4a2c5d943a15a105faa5ab23572
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/01/2020
ms.locfileid: "75589388"
---
# <a name="symbol-path-command"></a>Ruta de acceso de símbolos (Comando)
Establece la lista de directorios para que el depurador busque símbolos.

## <a name="syntax"></a>Sintaxis

```
Debug.SymbolPath pathname1;pathname2;... pathnameN
```

## <a name="arguments"></a>Argumentos
`pathname`

Opcional. Lista de rutas de acceso delimitada por puntos y comas para que el depurador busque símbolos.

## <a name="remarks"></a>Comentarios
Si no se especifica ningún `pathname`, el comando muestra las rutas de acceso de símbolos actuales.

## <a name="example"></a>Ejemplo
En este ejemplo, se agregan dos rutas de acceso a la lista de directorios de símbolos.

```
Debug.SymbolPath C:\Symbol Path 1;C:\Symbol Path 2
```

## <a name="example"></a>Ejemplo
En este ejemplo, se muestra una lista delimitada por puntos y comas de rutas de acceso de símbolos actuales.

```
Debug.SymbolPath
```

## <a name="see-also"></a>Vea también

- [Ventana Comandos](../../ide/reference/command-window.md)
- [Comandos de Visual Studio](../../ide/reference/visual-studio-commands.md)
