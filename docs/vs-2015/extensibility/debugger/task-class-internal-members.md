---
title: 'Clase de tarea: miembros internos | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, Task class [.NET Framework]
- Task class [.NET Framework debug engines]
ms.assetid: 28e47c3b-9323-424a-80ac-6cc3bf19e09b
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ef0cd907c25a90ee90e3ed23a773d0ae8ba0ce1f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "90842522"
---
# <a name="task-class---internal-members"></a>Clase de tarea: miembros internos
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

En este tema se describen los miembros internos de la <xref:System.Threading.Tasks.Task?displayProperty=fullName> clase que le ayudan a implementar un depurador personalizado. Para obtener información general sobre esta clase, vea el <xref:System.Threading.Tasks.Task> tema de referencia.  
  
 **Espacio de nombres:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Ensamblado:** mscorlib (en mscorlib.dll)  
  
 Dado que no puede tener acceso a estos miembros internos desde el .NET Framework, se proporciona la siguiente sintaxis en el lenguaje intermedio común (CIL).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
.class public auto ansi System.Threading.Tasks.Task  
       extends System.Object  
       implements System.Threading.IThreadPoolWorkItem,  
                  System.IAsyncResult,  
                  System.IDisposable,  
                  System.Threading.ICancelableOperation  
```  
  
## <a name="members"></a>Miembros  
  
### <a name="methods"></a>Métodos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[SetNotificationForWaitCompletion (Método)](../../extensibility/debugger/setnotificationforwaitcompletion-method.md)|Establece o borra el bit de estado de TASK_STATE_WAIT_COMPLETION_NOTIFICATION.|  
|[NotifyDebuggerOfWaitCompletion (Método)](../../extensibility/debugger/notifydebuggerofwaitcompletion-method.md)|Método de marcador de posición utilizado como destino de punto de interrupción por el depurador.|  
  
### <a name="fields"></a>Campos  
  
|NOMBRE|Descripción|  
|----------|-----------------|  
|[m_action](../../extensibility/debugger/m-action-field.md)|Delegado que representa el código que se va a ejecutar en el <xref:System.Threading.Tasks.Task> objeto.|  
|[m_contingentProperties](../../extensibility/debugger/m-contingentproperties-field.md)|Almacena propiedades adicionales del <xref:System.Threading.Tasks.Task> objeto.|  
|[m_parent](../../extensibility/debugger/m-parent-field.md)|Campo de respaldo de la <xref:System.Threading.Tasks.Task?displayProperty=fullName> propiedad primaria.|  
|[m_stateFlags](../../extensibility/debugger/m-stateflags-field.md)|Almacena información sobre el estado actual del <xref:System.Threading.Tasks.Task> objeto.|  
|[m_stateObject](../../extensibility/debugger/m-stateobject-field.md)|Objeto que representa los datos que usará la acción.|  
|[m_taskId](../../extensibility/debugger/m-taskid-field.md)|Campo de respaldo de la <xref:System.Threading.Tasks.Task.Id%2A?displayProperty=fullName> propiedad.|  
|[s_taskIdCounter](../../extensibility/debugger/s-taskidcounter-field.md)|Siguiente identificador disponible para un <xref:System.Threading.Tasks.Task> objeto.|  
|[TASK_STATE_CANCELED](../../extensibility/debugger/task-state-canceled-field.md)|Indica que la tarea se canceló antes de alcanzar el estado de ejecución, o que la tarea confirmó su cancelación y se completó sin excepción.|  
|[TASK_STATE_EXECUTED](../../extensibility/debugger/task-state-executed-field.md)|Indica que la tarea se está ejecutando.|  
|[TASK_STATE_FAULTED](../../extensibility/debugger/task-state-faulted-field.md)|Indica que la tarea se completó debido a una excepción no controlada.|  
|[TASK_STATE_RAN_TO_COMPLETION](../../extensibility/debugger/task-state-ran-to-completion-field.md)|Indica que la tarea completó la ejecución correctamente.|  
|[TASK_STATE_WAITING_ON_CHILDREN](../../extensibility/debugger/task-state-waiting-on-children-field.md)|Indica que la tarea ha terminado de ejecutar su delegado y está esperando implícitamente que finalicen las tareas secundarias asociadas.|  
  
## <a name="remarks"></a>Notas  
 Los métodos internos siguientes son útiles para un motor de depuración porque marcan la entrada para la <xref:System.Threading.Tasks.Task> ejecución del código:  
  
- `Execute`  
  
- `ExecuteEntry`  
  
- `ExecuteWithThreadLocal`  
  
- `Finish`  
  
- `InnerInvoke`  
  
- `InternalWait`  
  
## <a name="see-also"></a>Consulte también  
 <xref:System.Threading.Tasks.Task?displayProperty=fullName>   
 [Datos internos de extensiones paralelas para .NET Framework](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)
