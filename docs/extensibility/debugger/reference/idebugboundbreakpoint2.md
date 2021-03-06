---
title: IDebugBoundBreakpoint2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBoundBreakpoint2
helpviewer_keywords:
- IDebugBoundBreakpoint2 interface
ms.assetid: df33c52e-ded2-48a0-951d-1f36c8fc922e
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f4d22b10085baefeb3a0286c1b4edcb5876c0dac
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80735428"
---
# <a name="idebugboundbreakpoint2"></a>IDebugBoundBreakpoint2
Esta interfaz representa un punto de interrupción que está enlazado a una ubicación de código.

## <a name="syntax"></a>Sintaxis

```
IDebugBoundBreakpoint2 : IUnknown
```

## <a name="notes-for-implementers"></a>Notas para los implementadores
 El motor de depuración (DE) implementa esta interfaz como parte de su compatibilidad con los puntos de interrupción.

## <a name="notes-for-callers"></a>Notas para llamadores
 Una llamada a [BIND](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) crea esta interfaz. Las llamadas a [GetBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getbreakpoint.md) y [Next](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-next.md) también pueden obtener esta interfaz.

## <a name="methods-in-vtable-order"></a>Métodos en orden de Vtable
 En la tabla siguiente se muestran los métodos de `IDebugBoundBreakpoint2` .

|Método|Descripción|
|------------|-----------------|
|[GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getpendingbreakpoint.md)|Obtiene el punto de interrupción pendiente en el que se creó el punto de interrupción enlazado especificado.|
|[GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)|Obtiene el estado de este punto de interrupción enlazado.|
|[GetHitCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-gethitcount.md)|Obtiene el número de llamadas actual para este punto de interrupción enlazado.|
|[GetBreakpointResolution](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md)|Obtiene la resolución del punto de interrupción que describe este punto de interrupción.|
|[Habilitar](../../../extensibility/debugger/reference/idebugboundbreakpoint2-enable.md)|Habilita o deshabilita el punto de interrupción.|
|[SetHitCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-sethitcount.md)|Establece el número de llamadas para este punto de interrupción enlazado.|
|[SetCondition](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setcondition.md)|Establece o cambia la condición asociada a este punto de interrupción enlazado.|
|[SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md)|Establece o cambia el número de pases asociado a este punto de interrupción enlazado.|
|[Eliminar](../../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md)|Elimina el punto de interrupción.|

## <a name="requirements"></a>Requisitos
 Encabezado: msdbg. h

 Espacio de nombres: Microsoft. VisualStudio. Debugger. Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [GetBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getbreakpoint.md)
- [Siguiente](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-next.md)
- [Volver](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)
