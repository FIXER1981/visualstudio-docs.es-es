---
title: IDebugProgram2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2
helpviewer_keywords:
- IDebugProgram2 interface
ms.assetid: 8d73df73-cfff-4b8b-b426-d6051edb1939
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: daad54225170366d98a2df3465c7dba952098c4e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56713079"
---
# <a name="idebugprogram2"></a>IDebugProgram2
Esta interfaz representa un programa que se está ejecutando en un proceso.

## <a name="syntax"></a>Sintaxis

```
IDebugProgram2 : IUnknown
```

## <a name="notes-for-implementers"></a>Notas para los implementadores
 El motor de depuración (DE) y un proveedor de puerto personalizado implementan esta interfaz para representar un programa en un proceso. El Administrador de depuración de la sesión (SDM) también implementa esta interfaz para proporcionar información a [adjuntar](../../../extensibility/debugger/reference/idebugprogram2-attach.md).

## <a name="notes-for-callers"></a>Notas para los llamadores
 El [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) evento devuelve esta interfaz para un nuevo programa. Esta interfaz también se utiliza como un parámetro para muchos de los métodos en varias interfaces.

## <a name="methods-in-vtable-order"></a>Métodos en orden de Vtable
 La tabla siguiente muestran los métodos de `IDebugProgram2`.

|Método|Descripción|
|------------|-----------------|
|[EnumThreads](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md)|Enumera los subprocesos que se ejecutan en este programa.|
|[GetName](../../../extensibility/debugger/reference/idebugprogram2-getname.md)|Obtiene el nombre del programa.|
|[GetProcess](../../../extensibility/debugger/reference/idebugprogram2-getprocess.md)|Obtiene el proceso que se ejecuta este programa en.|
|[Terminate](../../../extensibility/debugger/reference/idebugprogram2-terminate.md)|Termina este programa.|
|[Asociar](../../../extensibility/debugger/reference/idebugprogram2-attach.md)|Se asocia a este programa.|
|[CanDetach](../../../extensibility/debugger/reference/idebugprogram2-candetach.md)|Determina si puede separar un motor de depuración (DE) desde el programa.|
|[Desasociar](../../../extensibility/debugger/reference/idebugprogram2-detach.md)|Desasocia al depurador de este programa.|
|[GetProgramId](../../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)|Obtiene un identificador único global para este programa.|
|[GetDebugProperty](../../../extensibility/debugger/reference/idebugprogram2-getdebugproperty.md)|Obtiene las propiedades del programa.|
|[Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md)|Continúa ejecutando este programa desde un estado detenido. Se borra cualquier estado de ejecución anterior.|
|[Continue](../../../extensibility/debugger/reference/idebugprogram2-continue.md)|Continúa ejecutando este programa desde un estado detenido. Se conserva ningún estado de ejecución anterior.|
|[Step](../../../extensibility/debugger/reference/idebugprogram2-step.md)|Realiza un paso.|
|[CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)|Las solicitudes que este programa detener la ejecución del siguiente momento uno de su código de ejecuciones de subprocesos.|
|[GetEngineInfo](../../../extensibility/debugger/reference/idebugprogram2-getengineinfo.md)|Obtiene el nombre y el identificador del motor de depuración (DE) al ejecutar este programa.|
|[EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)|Enumera los contextos de código para una posición determinada en un archivo de origen.|
|[GetMemoryBytes](../../../extensibility/debugger/reference/idebugprogram2-getmemorybytes.md)|Obtiene los bytes de memoria para este programa.|
|[GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)|Obtiene la secuencia de desensamblado de este programa o parte de este programa.|
|[EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md)|Enumera los módulos que este programa se ha cargado y se está ejecutando.|
|[GetENCUpdate](../../../extensibility/debugger/reference/idebugprogram2-getencupdate.md)|Obtiene la actualización de editar y continuar (ENC) para este programa.<br /><br /> Un motor de depuración no implementa este método (siempre debe devolver `E_NOTIMPL`).|
|[EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md)|Enumera las rutas de acceso del código de este programa.|
|[WriteDump](../../../extensibility/debugger/reference/idebugprogram2-writedump.md)|Escribe un volcado de memoria en un archivo.|

## <a name="requirements"></a>Requisitos
 Encabezado: msdbg.h

 Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="remarks"></a>Comentarios
 Un programa es un contenedor de subproceso que se ejecuta en una arquitectura de tiempo de ejecución determinada, mientras que un proceso se compone de uno o más programas.

## <a name="see-also"></a>Vea también
- [Interfaces básicas](../../../extensibility/debugger/reference/core-interfaces.md)
- [GetProgram](../../../extensibility/debugger/reference/idebugthread2-getprogram.md)
- [Siguiente](../../../extensibility/debugger/reference/ienumdebugprograms2-next.md)
- [Event](../../../extensibility/debugger/reference/idebugportevents2-event.md)
- [Asociar](../../../extensibility/debugger/reference/idebugengine2-attach.md)
- [DestroyProgram](../../../extensibility/debugger/reference/idebugengine2-destroyprogram.md)
- [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
- [Attach_V7](../../../extensibility/debugger/reference/idebugprogramnode2-attach-v7.md)