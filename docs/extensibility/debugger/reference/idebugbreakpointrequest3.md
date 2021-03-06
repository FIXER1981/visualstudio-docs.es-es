---
title: IDebugBreakpointRequest3 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBreakpointRequest3
helpviewer_keywords:
- IDebugBreakpointRequest3
ms.assetid: 8a042beb-b319-48e3-b3c8-9c8336ab371b
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 505b0c0b05fa0f14578d770abec6c43ed6b80b01
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80734820"
---
# <a name="idebugbreakpointrequest3"></a>IDebugBreakpointRequest3
Esta interfaz representa la información necesaria para crear y enlazar cualquier tipo de punto de interrupción. Es una extensión de [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md).

## <a name="syntax"></a>Sintaxis

```
IDebugBreakpointRequest3 : IDebugBreakpointRequest2
```

## <a name="notes-for-implementers"></a>Notas para los implementadores
 Normalmente, el administrador de depuración de sesión (SDM) implementa esta interfaz.

## <a name="notes-for-callers"></a>Notas para llamadores
 El motor DE depuración (DE) obtiene acceso a esta interfaz llamando a [QueryInterface](/cpp/atl/queryinterface) en la interfaz IDebugBreakpointRequest2 recibida en una llamada a [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md).

## <a name="methods-in-vtable-order"></a>Métodos en orden de Vtable
 Además de los métodos heredados de [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md), la `IDebugBreakpointRequest3` interfaz expone el método siguiente.

|Método|Descripción|
|------------|-----------------|
|[GetRequestInfo2](../../../extensibility/debugger/reference/idebugbreakpointrequest3-getrequestinfo2.md)|Obtiene la información de solicitud de punto de interrupción que describe esta solicitud de punto de interrupción.|

## <a name="remarks"></a>Observaciones
 Esta interfaz se utiliza para proporcionar información adicional al DE a través de la estructura DE [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) . Esta información adicional incluye el identificador de proveedor DE DE (en forma de un GUID), el nombre de un punto de seguimiento y el nombre de una restricción de punto de interrupción.

## <a name="requirements"></a>Requisitos
 Encabezado: msdbg. h

 Espacio de nombres: Microsoft. VisualStudio. Debugger. Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)
- [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)
