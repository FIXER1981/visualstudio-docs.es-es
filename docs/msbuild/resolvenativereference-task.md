---
title: ResolveNativeReference (Tarea) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ResolveNativeReference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, ResolveNativeReference task
- ResolveNativeReference task [MSBuild]
ms.assetid: 56acd101-de77-4eec-92c6-f5c6d2187579
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0f18549fece2db8a4a758dee17f6b4b1283d97e4
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56617761"
---
# <a name="resolvenativereference-task"></a>ResolveNativeReference (tarea)
Resuelve las referencias nativas. Implementa la clase <xref:Microsoft.Build.Tasks.ResolveNativeReference>. Esta clase admite la infraestructura de .NET Framework, que no está diseñada para utilizarse directamente desde el código.

## <a name="task-parameters"></a>Parámetros de tareas
 En la siguiente tabla se describen los parámetros de la tarea `ResolveNativeReference` .

|Parámetro|Descripción|
|---------------|-----------------|
|`AdditionalSearchPaths`|Parámetro <xref:System.String?displayProperty=fullName>`[]` requerido.<br /><br /> Obtiene o establece las rutas de acceso de búsqueda para resolver identidades de ensamblado de las referencias nativas.|
|`ContainedComComponents`|Parámetro de salida <xref:Microsoft.Build.Framework.ITaskItem>`[]` opcional.<br /><br /> Obtiene o establece los componentes COM del ensamblado nativo.|
|`ContainedLooseEtcFiles`|Parámetro de salida <xref:Microsoft.Build.Framework.ITaskItem>`[]` opcional.<br /><br /> Obtiene o establece los archivos *Etc* dinámicos que figuran en el manifiesto nativo.|
|`ContainedLooseTlbFiles`|Parámetro de salida <xref:Microsoft.Build.Framework.ITaskItem>`[]` opcional.<br /><br /> Obtiene o establece los archivos *.tlb* dinámicos del ensamblado nativo.|
|`ContainedPrerequisiteAssemblies`|Parámetro de salida <xref:Microsoft.Build.Framework.ITaskItem>`[]` opcional.<br /><br /> Obtiene o establece los ensamblados que deben estar presentes para poder usar el manifiesto.|
|`ContainedTypeLibraries`|Parámetro de salida <xref:Microsoft.Build.Framework.ITaskItem>`[]` opcional.<br /><br /> Obtiene o establece las bibliotecas de tipos del ensamblado nativo.|
|`ContainingReferenceFiles`|Parámetro de salida <xref:Microsoft.Build.Framework.ITaskItem>`[]` opcional.<br /><br /> Obtiene o establece los archivos de referencia.|
|`NativeReferences`|Parámetro <xref:Microsoft.Build.Framework.ITaskItem>`[]` requerido.<br /><br /> Obtiene o establece las referencias de ensamblado nativas Win32.|

## <a name="remarks"></a>Comentarios
 Además de los parámetros mencionados anteriormente, esta tarea hereda los parámetros de la clase <xref:Microsoft.Build.Tasks.TaskExtension>, que a su vez hereda de la clase <xref:Microsoft.Build.Utilities.Task>. Para obtener una lista de estos parámetros adicionales y sus descripciones, consulte [TaskExtension base class](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Vea también
- [Tareas](../msbuild/msbuild-tasks.md)
- [Referencia de tareas](../msbuild/msbuild-task-reference.md)