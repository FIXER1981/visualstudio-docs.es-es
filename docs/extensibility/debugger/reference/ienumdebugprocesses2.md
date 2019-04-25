---
title: IEnumDebugProcesses2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugProcesses2
helpviewer_keywords:
- IEnumDebugProcesses2
ms.assetid: 06a1368f-10f0-44eb-af61-e388c2327111
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d3f76746c29bff7dce76c2eda97fbd1287e5906a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56698500"
---
# <a name="ienumdebugprocesses2"></a>IEnumDebugProcesses2
Esta interfaz enumera los procesos que se ejecutan en un puerto de depuración.

## <a name="syntax"></a>Sintaxis

```
IEnumDebugProcesses : IUnknown
```

## <a name="notes-for-implementers"></a>Notas para los implementadores
 Un proveedor de puerto personalizado implementa esta interfaz para proporcionar una lista de procesos que se ejecutan en un puerto.

## <a name="notes-for-callers"></a>Notas para los llamadores
 Llamadas visuales Studio [EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md) para obtener esta interfaz.

## <a name="methods-in-vtable-order"></a>Métodos en orden de Vtable
 La tabla siguiente muestran los métodos de `IEnumDebugProcesses2`.

|Método|Descripción|
|------------|-----------------|
|[Siguiente](../../../extensibility/debugger/reference/ienumdebugprocesses2-next.md)|Recupera un número especificado de procesos en una secuencia de enumeración.|
|[Skip](../../../extensibility/debugger/reference/ienumdebugprocesses2-skip.md)|Omite un número especificado de procesos en una secuencia de enumeración.|
|[Reset](../../../extensibility/debugger/reference/ienumdebugprocesses2-reset.md)|Restablece una secuencia de enumeración al principio.|
|[Clone](../../../extensibility/debugger/reference/ienumdebugprocesses2-clone.md)|Crea un enumerador que contiene el mismo estado de enumeración que el enumerador actual.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugprocesses2-getcount.md)|Obtiene el número de procesos en un enumerador.|

## <a name="remarks"></a>Comentarios
 Visual Studio usa esta interfaz para rellenar el **procesos** ventana.

## <a name="requirements"></a>Requisitos
 Encabezado: msdbg.h

 Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [Interfaces básicas](../../../extensibility/debugger/reference/core-interfaces.md)
- [EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)