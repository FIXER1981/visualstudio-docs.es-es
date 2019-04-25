---
title: Procedimiento Mostrar una lista de elementos separados por comas | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, separating items with semicolons
- MSBuild, formatting item collections
ms.assetid: 3cae844c-7c6d-4144-82dc-efad10ba458f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b01e39569207065fac9c28d093267348a829d73f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56610468"
---
# <a name="how-to-display-an-item-list-separated-with-commas"></a>Procedimiento Mostrar una lista de elementos separados por comas
Cuando se trabaja con listas de elementos en [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] ([!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]), a veces resulta útil mostrar el contenido de las listas de elementos de tal forma que sea fácil de leer. O puede que tenga una tarea que toma una lista de elementos separados con una cadena de separación especial. En ambos casos, puede especificar una cadena de separación para una lista de elementos.

## <a name="separate-items-in-a-list-with-commas"></a>Separar los elementos de una lista con comas
De manera predeterminada, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] usa signos de punto y coma para separar los elementos de una lista. Por ejemplo, considere un elemento `Message` con el valor siguiente:

`<Message Text="This is my list of TXT files: @(TXTFile)"/>`

Cuando la lista de elementos `@(TXTFile)` contiene los elementos *App1.txt*, *App2.txt* y *App3.txt*, el mensaje es:

`This is my list of TXT files: App1.txt;App2.txt;App3.txt`

Si quiere cambiar el comportamiento predeterminado, puede especificar su propio separador. La sintaxis para especificar un separador de lista de elementos es:

`@(ItemListName, '<separator>')`

El separador puede ser un solo carácter o una cadena y debe incluirse entre comillas simples.

#### <a name="to-insert-a-comma-and-a-space-between-items"></a>Para insertar una coma y un espacio entre los elementos

- Use una notación de elemento similar a la siguiente:

    `@(TXTFile, ', ')`

## <a name="example"></a>Ejemplo
En este ejemplo, la tarea [Exec](../msbuild/exec-task.md) ejecuta la herramienta findstr para buscar cadenas de texto especificadas en el archivo, *Phrases.txt*. En el comando findstr, las cadenas de búsqueda literal se indican mediante el modificador **-c:**, por lo que el separador de elementos `-c:` se inserta entre los elementos de la lista de elementos `@(Phrase)`.

En este ejemplo, el comando de línea de comandos equivalente es:

`findstr /i /c:hello /c:world /c:msbuild phrases.txt`

```xml
<Project DefaultTargets = "Find"
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >

    <ItemGroup>
        <Phrase Include="hello"/>
        <Phrase Include="world"/>
        <Phrase Include="msbuild"/>
    </ItemGroup>

    <Target Name = "Find">
        <!-- Find some strings in a file -->
        <Exec Command="findstr /i /c:@(Phrase, ' /c:') phrases.txt"/>
    </Target>
</Project>
```

## <a name="see-also"></a>Vea también
- [Referencia de MSBuild](../msbuild/msbuild-reference.md)
- [Elementos](../msbuild/msbuild-items.md)
