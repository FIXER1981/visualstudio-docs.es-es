---
title: Elemento Task de UsingTask (MSBuild) | Microsoft Docs
ms.date: 03/13/2017
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Task element [MSBuild]
- <Task> element [MSBuild]
ms.assetid: 49d8741b-f1ea-4470-94fd-a1ac27341a6a
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 36644a6b21092361d92dba5f0886eb4198884995
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "78263193"
---
# <a name="task-element-of-usingtask-msbuild"></a>Elemento Task de UsingTask (MSBuild)

Contiene los datos que se pasen a `UsingTask` `TaskFactory`. Para más información, consulte [Elemento UsingTask (MSBuild)](../msbuild/usingtask-element-msbuild.md).

 \<Project> \<UsingTask> \<Task>
 \<Task>

## <a name="syntax"></a>Sintaxis

```xml
<Task Evaluate="true/false" />
```

## <a name="attributes-and-elements"></a>Atributos y elementos

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`Evaluate`|Atributo Boolean opcional.<br /><br /> Si es `true`, MSBuild evalúa los elementos internos y expande los elementos y las propiedades antes de pasar la información a `TaskFactory` cuando se crea una instancia de la tarea.|

### <a name="child-elements"></a>Elementos secundarios

|Elemento|Descripción|
|-------------|-----------------|
|Datos|El texto entre las etiquetas `Task` se envía textual a `TaskFactory`.|

### <a name="parent-elements"></a>Elementos primarios

| Elemento | Descripción |
| - | - |
| [UsingTask](../msbuild/usingtask-element-msbuild.md) | Proporciona una manera de registrar las tareas en MSBuild. Puede haber cero o más elementos `UsingTask` en un proyecto. |

## <a name="example"></a>Ejemplo

 En el ejemplo siguiente se muestra cómo usar el elemento `Task` con un atributo `Evaluate`.

```xml
<UsingTask TaskName="MyTask" AssemblyName="My.Assembly" TaskFactory="MyTaskFactory">
       <ParameterGroup>
              <Parameter1 ParameterType="System.String" Required="False" Output="False"/>
              <Parameter2 ParameterType="System.Int" Required="True" Output="False"/>
              ...
</ParameterGroup>
       <Task Evaluate="true">
       ... Task factory-specific data ...
       </Task>
</UsingTask>
```

## <a name="see-also"></a>Vea también

- [Tareas](../msbuild/msbuild-tasks.md)
- [Referencia de tareas](../msbuild/msbuild-task-reference.md)
- [Referencia de esquema de archivo de proyecto](../msbuild/msbuild-project-file-schema-reference.md)
