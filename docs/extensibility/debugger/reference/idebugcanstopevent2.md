---
title: IDebugCanStopEvent2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCanStopEvent2
helpviewer_keywords:
- IDebugBreakpointRequest2 interface
ms.assetid: 784bd5b1-4a3f-4455-b313-c4c9a82555a5
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f0a3710756f02d7c622be94bab6c3056fb051827
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80734512"
---
# <a name="idebugcanstopevent2"></a>IDebugCanStopEvent2
Esta interfaz se usa para solicitar al administrador de depuración de la sesión (SDM) si se debe detener en la ubicación del código actual.

## <a name="syntax"></a>Sintaxis

```
IDebugCanStopEvent2 : IUknown
```

## <a name="notes-for-implementers"></a>Notas para los implementadores
 El motor DE depuración (DE) implementa esta interfaz para admitir la ejecución paso a paso a través del código fuente. La interfaz [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) debe implementarse en el mismo objeto que esta interfaz (el SDM usa [QueryInterface](/cpp/atl/queryinterface) para tener acceso a la `IDebugEvent2` interfaz).

 La implementación de esta interfaz debe comunicar la llamada del SDM de [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md) al motor de depuración. Por ejemplo, esto se puede hacer con un mensaje expuesto al subproceso de control de mensajes del motor de depuración o el objeto que implementa esta interfaz podría contener una referencia al motor de depuración y volver a llamar al motor de depuración con la marca pasada a `IDebugCanStopEvent2::CanStop` .

## <a name="notes-for-callers"></a>Notas para llamadores
 La DE puede enviar este método cada vez que se le pide que continúe la ejecución y el DE se recorre en código. Este evento se envía mediante la función de devolución de llamada [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) proporcionada por el SDM cuando se adjunta al programa que se está depurando.

## <a name="methods-in-vtable-order"></a>Métodos en orden de Vtable
 En la tabla siguiente se muestran los métodos de `IDebugCanStopEvent2` .

|Método|Descripción|
|------------|-----------------|
|[GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)|Obtiene el motivo de este evento.|
|[CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)|Especifica si el programa que se va a depurar debe detenerse en la ubicación de este evento (y enviar un evento que describe el motivo de la detención) o simplemente continuar la ejecución.|
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getdocumentcontext.md)|Obtiene el contexto del documento que describe la ubicación de este evento.|
|[GetCodeContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getcodecontext.md)|Obtiene el contexto de código que describe la ubicación de este evento.|

## <a name="remarks"></a>Observaciones
 El DE envía esta interfaz si el usuario realiza un paso en una función y el DE no encuentra ninguna información de depuración o existe información de depuración, pero el DE no sabe si el código fuente se puede mostrar para esa ubicación.

## <a name="requirements"></a>Requisitos
 Encabezado: msdbg. h

 Espacio de nombres: Microsoft. VisualStudio. Debugger. Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [IDebugStepCompleteEvent2](../../../extensibility/debugger/reference/idebugstepcompleteevent2.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
