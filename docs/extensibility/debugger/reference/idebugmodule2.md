---
title: IDebugModule2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModule2
helpviewer_keywords:
- IDebugModule2 interface
ms.assetid: 24c2a126-f4ab-4891-8509-8ef99b994c08
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a6d2e7ae091964cd810acfcddcc4ea5ab81943c4
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56719826"
---
# <a name="idebugmodule2"></a>IDebugModule2
Esta interfaz representa un módulo, es decir, una unidad ejecutable de un programa, como un archivo DLL.

## <a name="syntax"></a>Sintaxis

```
IDebugModule2 : IUnknown
```

## <a name="notes-for-implementers"></a>Notas para los implementadores
 El motor de depuración (DE) implementa esta interfaz para representar un módulo y para proporcionar acceso a información acerca de ese módulo.

## <a name="notes-for-callers"></a>Notas para los llamadores
 Una llamada a [GetModule](../../../extensibility/debugger/reference/idebugmoduleloadevent2-getmodule.md) devuelve esta interfaz. Los envíos DE la [IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md) interfaz para el Administrador de depuración de la sesión (SDM) mediante el [eventos](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) método.

 Esta interfaz también se puede devolver en un [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) estructura (que es devuelto por una llamada a [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)).

- [Siguiente](../../../extensibility/debugger/reference/ienumdebugmodules2-next.md) también devuelve esta interfaz ([EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) devuelve el [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md) interfaz).

## <a name="methods-in-vtable-order"></a>Métodos en orden de Vtable
 La tabla siguiente muestran los métodos de `IDebugModule2`.

|Método|Descripción|
|------------|-----------------|
|[GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)|Obtiene el [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) que describe este módulo.|
|[ReloadSymbols_Deprecated](../../../extensibility/debugger/reference/idebugmodule2-reloadsymbols-deprecated.md)|OBSOLETO. NO USE. Vuelve a cargar los símbolos para este módulo.|

## <a name="remarks"></a>Comentarios
 Información de módulos puede mostrarse en el **módulos** ventana del IDE.

## <a name="requirements"></a>Requisitos
 Encabezado: msdbg.h

 Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [Interfaces básicas](../../../extensibility/debugger/reference/core-interfaces.md)
- [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)
- [GetModule](../../../extensibility/debugger/reference/idebugmoduleloadevent2-getmodule.md)
- [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)
- [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)