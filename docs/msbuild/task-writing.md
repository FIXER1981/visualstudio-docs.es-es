---
title: Escribir tareas | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, writing tasks
- tasks, creating for MSBuild
- MSBuild, creating tasks
ms.assetid: 3ebc5f87-8f00-46fc-82a1-228f35a6823b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fdeab63dffaf7884484f46fbfe9eac2002514e52
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56629929"
---
# <a name="task-writing"></a>Escribir tareas
Las tareas proporcionan el código que se ejecuta durante el proceso de compilación. Las tareas están contenidas en destinos. En [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] se incluye una biblioteca de tareas típicas, y también puede crear sus propias tareas. Para más información sobre la biblioteca de tareas incluida en [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], consulte [Referencia de tareas](../msbuild/msbuild-task-reference.md).

## <a name="tasks"></a>Tareas
 Algunos ejemplos de tareas son [Copy](../msbuild/copy-task.md), que copia uno o más archivos, [MakeDir](../msbuild/makedir-task.md), que crea un directorio, y [Csc](../msbuild/csc-task.md), que compila archivos de código fuente [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]. Cada tarea se implementa como una clase .NET que, a su vez, implementa la interfaz <xref:Microsoft.Build.Framework.ITask>, definida en el ensamblado *Microsoft.Build.Framework.dll*.

 Al implementar una tarea, se pueden utilizar dos métodos:

-   Implementar la interfaz <xref:Microsoft.Build.Framework.ITask> directamente.

-   Derivar la clase de la clase del asistente, <xref:Microsoft.Build.Utilities.Task>, que se define en el ensamblado *Microsoft.Build.Utilities.dll*. La tarea implementa ITask y proporciona implementaciones predeterminadas de algunos miembros ITask. Además, el registro es más sencillo.

En ambos casos, debe agregar a la clase un método denominado `Execute`, que es el método al que se llama cuando se ejecuta la tarea. Este método no utiliza ningún parámetro y devuelve un valor `Boolean`: `true` si la tarea se realizó correctamente o `false` si se produjo un error. En el ejemplo siguiente se muestra una tarea que no realiza ninguna acción y devuelve `true`.

```csharp
using System;
using Microsoft.Build.Framework;
using Microsoft.Build.Utilities;

namespace MyTasks
{
    public class SimpleTask : Task
    {
        public override bool Execute()
        {
            return true;
        }
    }
}
```

 El siguiente archivo de proyecto ejecuta esta tarea:

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    <Target Name="MyTarget">
        <SimpleTask />
    </Target>
</Project>
```

 Mientras se ejecutan las tareas, también pueden recibir entradas del archivo del proyecto si crea las propiedades de .NET en la clase de tarea. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] establece inmediatamente estas propiedades antes de llamar al método `Execute` de la tarea. Para crear una propiedad de cadena, utilice código de tarea como:

```csharp
using System;
using Microsoft.Build.Framework;
using Microsoft.Build.Utilities;

namespace MyTasks
{
    public class SimpleTask : Task
    {
        public override bool Execute()
        {
            return true;
        }

        public string MyProperty { get; set; }
    }
}
```

 El siguiente archivo del proyecto ejecuta esta tarea y establece `MyProperty` al valor dado:

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
   <Target Name="MyTarget">
      <SimpleTask MyProperty="Value for MyProperty" />
   </Target>
</Project>
```

## <a name="register-tasks"></a>Registro de tareas
 Si un proyecto va a ejecutar una tarea, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] debe saber cómo localizar el ensamblado que contiene la clase de tarea. Las tareas se registran mediante el [elemento UsingTask (MSBuild)](../msbuild/usingtask-element-msbuild.md).

 El archivo de [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] *Microsoft.Common.Tasks* es un archivo de proyecto que contiene una lista de elementos `UsingTask` que registran todas las tareas que se proporcionan con [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Este archivo se incluye automáticamente al compilar cada proyecto. Si una tarea registrada en *Microsoft.Common.Tasks* también está registrada en el archivo del proyecto actual, este tiene prioridad; es decir, puede reemplazar una tarea predeterminada por una tarea que tenga el mismo nombre.

> [!TIP]
>  Para ver una lista de las tareas que se proporcionan con [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], puede visualizar el contenido de *Microsoft.Common.Tasks*.

## <a name="raise-events-from-a-task"></a>Generación de eventos de una tarea
 Si la tarea se deriva de la clase del asistente <xref:Microsoft.Build.Utilities.Task>, puede usar cualquiera de los siguientes métodos del asistente en la clase <xref:Microsoft.Build.Utilities.Task> para generar eventos que cualquier registrador registrado detectará y mostrará:

```csharp
public override bool Execute()
{
    Log.LogError("messageResource1", "1", "2", "3");
    Log.LogWarning("messageResource2");
    Log.LogMessage(MessageImportance.High, "messageResource3");
    ...
}
```

 Si la tarea implementa directamente <xref:Microsoft.Build.Framework.ITask>, todavía puede generar dichos eventos, pero debe utilizar la interfaz IBuildEngine. En el ejemplo siguiente se muestra una tarea que implementa ITask y genera un evento personalizado:

```csharp
public class SimpleTask : ITask
{
    public IBuildEngine BuildEngine { get; set; }

    public override bool Execute()
    {
        TaskEventArgs taskEvent =
            new TaskEventArgs(BuildEventCategory.Custom,
            BuildEventImportance.High, "Important Message",
           "SimpleTask");
        BuildEngine.LogBuildEvent(taskEvent);
        return true;
    }
}
```

## <a name="require-task-parameters-to-be-set"></a>Requisito de establecimiento de parámetros de tareas
 Puede marcar determinadas propiedades de la tarea como "necesarias", de modo que cualquier archivo del proyecto que ejecute la tarea debe establecer los valores de estas propiedades o se produce un error en la compilación. Aplique el atributo `[Required]` a la propiedad de .NET en la tarea como se indica a continuación:

```csharp
[Required]
public string RequiredProperty { get; set; }
```

 <xref:Microsoft.Build.Framework.RequiredAttribute> define el atributo `[Required]` en el espacio de nombres <xref:Microsoft.Build.Framework>.

## <a name="example"></a>Ejemplo

### <a name="description"></a>Descripción
 La clase [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] siguiente muestra una tarea que deriva de la clase del asistente <xref:Microsoft.Build.Utilities.Task>. Esta tarea devuelve `true`, lo que indica que se ha realizado correctamente.

### <a name="code"></a>Código

```csharp
using System;
using Microsoft.Build.Utilities;

namespace SimpleTask1
{
    public class SimpleTask1: Task
    {
        public override bool Execute()
        {
            // This is where the task would presumably do its work.
            return true;
        }
    }
}
```

## <a name="example"></a>Ejemplo

### <a name="description"></a>Descripción
 La clase [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] siguiente muestra una tarea que implementa la interfaz <xref:Microsoft.Build.Framework.ITask>. Esta tarea devuelve `true`, lo que indica que se ha realizado correctamente.

### <a name="code"></a>Código

```csharp
using System;
using Microsoft.Build.Framework;

namespace SimpleTask2
{
    public class SimpleTask2: ITask
    {
        //When implementing the ITask interface, it is necessary to
        //implement a BuildEngine property of type
        //Microsoft.Build.Framework.IBuildEngine. This is done for
        //you if you derive from the Task class.
        public IBuildEngine BuildEngine { get; set; }

        // When implementing the ITask interface, it is necessary to
        // implement a HostObject property of type object.
        // This is done for you if you derive from the Task class.
        public object HostObject { get; set; }

        public bool Execute()
        {
            // This is where the task would presumably do its work.
            return true;
        }
    }
}
```

## <a name="example"></a>Ejemplo

### <a name="description"></a>Descripción
 Esta clase [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] muestra una tarea que deriva de la clase del asistente <xref:Microsoft.Build.Utilities.Task>. Tiene una propiedad de cadena necesaria y genera un evento que todos los registradores registrados muestran.

### <a name="code"></a>Código
 [!code-csharp[msbuild_SimpleTask3#1](../msbuild/codesnippet/CSharp/task-writing_1.cs)]

## <a name="example"></a>Ejemplo

### <a name="description"></a>Descripción
 En el ejemplo siguiente se muestra un archivo del proyecto que invoca la tarea del ejemplo anterior, SimpleTask3.

### <a name="code"></a>Código

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    <UsingTask TaskName="SimpleTask3.SimpleTask3"
        AssemblyFile="SimpleTask3\bin\debug\simpletask3.dll"/>

    <Target Name="MyTarget">
        <SimpleTask3 MyProperty="Hello!"/>
    </Target>
</Project>
```

## <a name="see-also"></a>Vea también
- [Referencia de tareas](../msbuild/msbuild-task-reference.md)
