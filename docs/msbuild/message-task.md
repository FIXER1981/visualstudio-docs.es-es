---
title: Message (Tarea) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Message
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Message task
- Message task [MSBuild]
ms.assetid: 2293309d-42b6-46dc-9684-8c146f66bc28
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 264ff3a5e64b756020648e888f7817e12702659f
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "78865367"
---
# <a name="message-task"></a>Message (tarea)

Registra un mensaje durante una compilación.

## <a name="parameters"></a>Parámetros

 En la siguiente tabla se describen los parámetros de la tarea `Message` .

|Parámetro|Descripción|
|---------------|-----------------|
|`Importance`|Parámetro `String` opcional.<br /><br /> Especifica la importancia del mensaje. Este parámetro puede tener un valor de `high`, `normal` o `low`. El valor predeterminado es `normal`.|
|`Text`|Parámetro `String` opcional.<br /><br /> El texto del error que se va a registrar.|

## <a name="remarks"></a>Comentarios

 La tarea `Message` permite a los proyectos de MSBuild enviar mensajes a los registradores en etapas diferentes del proceso de compilación.

 Si el parámetro `Condition` se evalúa como `true`, se registrará el valor del parámetro `Text` y la compilación seguirá ejecutándose. Si no existe un parámetro `Condition`, se registra el texto del mensaje. Para obtener más información sobre los registros, vea [Obtener registros de compilación con MSBuild](../msbuild/obtaining-build-logs-with-msbuild.md).

 De forma predeterminada, el mensaje se envía a todos los registradores registrados. El registrador interpreta el parámetro `Importance`. Habitualmente, un mensaje establecido en `high` se envía cuando el nivel de detalle del registrador está establecido en <xref:Microsoft.Build.Framework.LoggerVerbosity>.`Minimal` o superior. Cuando el nivel de detalle del registrador está establecido en <xref:Microsoft.Build.Framework.LoggerVerbosity>.`Detailed`, se envía un mensaje establecido en `low`.

 Además de los parámetros mencionados anteriormente, esta tarea hereda los parámetros de la clase <xref:Microsoft.Build.Tasks.TaskExtension>, que a su vez hereda de la clase <xref:Microsoft.Build.Utilities.Task>. Para obtener una lista de estos parámetros adicionales y sus descripciones, consulte [TaskExtension base class](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Ejemplo

 El siguiente ejemplo de código registra mensajes para todos los registradores registrados.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    <Target Name="DisplayMessages">
        <Message Text="Project File Name = $(MSBuildProjectFile)" />
        <Message Text="Project Extension = $(MSBuildProjectExtension)" />
    </Target>
    ...
</Project>
```

## <a name="see-also"></a>Vea también

- [Referencia de tareas](../msbuild/msbuild-task-reference.md)
- [Obtener registros de compilación](../msbuild/obtaining-build-logs-with-msbuild.md)
