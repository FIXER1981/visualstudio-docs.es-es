---
title: IDebugEntryPointEvent2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEntryPointEvent2
helpviewer_keywords:
- IDebugEntryPointEvent2 interface
ms.assetid: a15d1cc3-97b7-438c-8d24-c23149708f42
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d682c43a8d1714ddcd32fc310db98b648a5a32af
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56715989"
---
# <a name="idebugentrypointevent2"></a>IDebugEntryPointEvent2
El motor de depuración (DE) envía esta interfaz para el Administrador de depuración de la sesión (SDM) cuando el programa que se va a ejecutar la primera instrucción de código de usuario.

## <a name="syntax"></a>Sintaxis

```
IDebugEntryPointEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Notas para los implementadores
 La DE implementa esta interfaz como parte de su funcionamiento normal. El [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) interfaz debe implementarse en el mismo objeto que esta interfaz. Usa el SDM [QueryInterface](/cpp/atl/queryinterface) para tener acceso a la `IDebugEvent2` interfaz.

## <a name="notes-for-callers"></a>Notas para los llamadores
 La DE crea y envía este objeto de evento cuando el programa que se está depurando se ha cargado y está listo para ejecutar la primera instrucción de código de usuario. El evento se envía mediante la [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) función de devolución de llamada que proporciona el SDM cuando adjunta al programa que se está depurando.

## <a name="remarks"></a>Comentarios
- [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md) se envía cuando el programa que se va a ejecutar la primera instrucción. Por ejemplo, `IDebugEntryPoint2` se envía cuando el programa que se va a ejecutar el usuario `main` función.

 Cuando se envía la DE `IDebugEntryPointEvent2`, debe ser la posición actual del código en la primera instrucción del código de usuario, como `main`.

## <a name="requirements"></a>Requisitos
 Encabezado: msdbg.h

 Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)