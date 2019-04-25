---
title: -LCID (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- language default
- locale IDs, setting for IDE
- Devenv, /L switch
- Devenv, /LCID switch
- locale IDs
- L Devenv switch
- /L Devenv switch
- LCID devenv switch
- /LCID Devenv switch
ms.assetid: 3a3f4e70-ea66-4351-9d62-acb1dec30e8e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: deb2ce5eba108127dce82bab77fe7ed4fb78fb14
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55947047"
---
# <a name="lcid-devenvexe"></a>/LCID (devenv.exe)

Establece el idioma predeterminado usado para texto, moneda y otros valores en el IDE.

## <a name="syntax"></a>Sintaxis

```shell
devenv {/LCID|/L} LocaleID
```

## <a name="arguments"></a>Argumentos

- *LocaleID*

  Obligatorio. Identificador de configuración regional (LCID) del idioma que especifique.

## <a name="remarks"></a>Comentarios

Carga el IDE y establece el idioma natural predeterminado para el entorno. Este cambio persiste entre sesiones y, en el IDE, se muestra en **Herramientas** > **Opciones** > **Entorno** > **Configuración internacional** > **cuadro Idioma**.

Si el idioma especificado no está disponible en el sistema, se omitirá el modificador `/LCID`.

En la tabla siguiente se indican los LCID de los idiomas que admite Visual Studio.

|Lenguaje|LCID|
|--------------|----------|
|Chino (simplificado)|2052|
|Chino (tradicional)|1028|
|Inglés|3082|
|Francés|1036|
|Alemán|1031|
|Italiano|1040|
|Japonés|1041|
|Coreano|1042|
|Español|3082|

## <a name="example"></a>Ejemplo

En este ejemplo se carga el IDE con cadenas de recursos en inglés.

```shell
devenv /LCID 1033
```

## <a name="see-also"></a>Vea también

- [Modificadores de línea de comandos para Devenv](../../ide/reference/devenv-command-line-switches.md)
- [Configuración internacional, Entorno, Opciones (Cuadro de diálogo)](../../ide/reference/international-settings-environment-options-dialog-box.md)
- [Personalizar los diseños de ventana](../../ide/customizing-window-layouts-in-visual-studio.md)