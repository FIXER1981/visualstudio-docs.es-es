---
title: ReadLinesFromFile (Tarea) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ReadLinesFromFile
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, ReadLinesFromFile task
- ReadLinesFromFile task [MSBuild]
ms.assetid: a18af929-b53a-4d9e-b7bf-e3d3737ee85f
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7c926c131fab101563841bea3362e88e27674226
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "77632906"
---
# <a name="readlinesfromfile-task"></a>ReadLinesFromFile (tarea)

Lee una lista de elementos de un archivo de texto.

## <a name="parameters"></a>Parámetros

 En la siguiente tabla se describen los parámetros de la tarea `ReadLinesFromFile`.

|Parámetro|Description|
|---------------|-----------------|
|`File`|Parámetro <xref:Microsoft.Build.Framework.ITaskItem> requerido.<br /><br /> Especifica el archivo que se va a leer. El archivo debe tener un elemento en cada línea.|
|`Lines`|Parámetro de salida <xref:Microsoft.Build.Framework.ITaskItem>`[]` opcional.<br /><br /> Contiene las líneas leídas del archivo.|

## <a name="remarks"></a>Observaciones

 Además de los parámetros mencionados anteriormente, esta tarea hereda los parámetros de la clase <xref:Microsoft.Build.Tasks.TaskExtension>, que a su vez hereda de la clase <xref:Microsoft.Build.Utilities.Task>. Para obtener una lista de estos parámetros adicionales y sus descripciones, consulte [TaskExtension base class](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Ejemplo

 En el ejemplo siguiente se usa la tarea `ReadLinesFromFile` para crear elementos de una lista de un archivo de texto. Los elementos leídos del archivo se almacenan en la colección de elementos `ItemsFromFile`.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <ItemGroup>
        <MyTextFile Include="Items.txt"/>
    </ItemGroup>

    <Target Name="ReadFromFile">
        <ReadLinesFromFile
            File="@(MyTextFile)" >
            <Output
                TaskParameter="Lines"
                ItemName="ItemsFromFile"/>
        </ReadLinesFromFile>
    </Target>

</Project>
```

## <a name="see-also"></a>Vea también

- [Referencia de tareas](../msbuild/msbuild-task-reference.md)
- [Conceptos de MSBuild](../msbuild/msbuild-concepts.md)
- [Tareas](../msbuild/msbuild-tasks.md)
