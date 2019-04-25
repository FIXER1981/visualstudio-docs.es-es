---
title: IDebugFunctionPosition2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugFunctionPosition2
helpviewer_keywords:
- IDebugFunctionPosition2 interface
ms.assetid: a835f65b-91b0-48ad-8485-04534c814b1b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: faed38853aa7d0d925a3b1e598627cf1a55166d1
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689920"
---
# <a name="idebugfunctionposition2"></a>IDebugFunctionPosition2
Esta interfaz representa una posición abstracta de una función en un documento de origen.

## <a name="syntax"></a>Sintaxis

```
IDebugFunctionPosition2 : IUnknown
```

## <a name="notes-for-implementers"></a>Notas para los implementadores
 El motor de depuración (DE) implementa esta interfaz para representar la posición de una función dentro de un documento de origen.

## <a name="notes-for-callers"></a>Notas para los llamadores
 Esta interfaz se suministra como parte de un [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) union (específicamente, un [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md) estructura) que a su vez forma parte de la [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) estructura que se utiliza en la creación de un punto de interrupción pendiente.

## <a name="methods-in-vtable-order"></a>Métodos en orden de Vtable
 La tabla siguiente muestran los métodos de `IDebugFunctionPosition2`.

|Método|Descripción|
|------------|-----------------|
|[GetFunctionName](../../../extensibility/debugger/reference/idebugfunctionposition2-getfunctionname.md)|Obtiene el nombre de esta posición es relativa a la función.|
|[GetOffset](../../../extensibility/debugger/reference/idebugfunctionposition2-getoffset.md)|Obtiene el desplazamiento desde el principio de la función.|

## <a name="remarks"></a>Comentarios
 En concreto, la posición representada por esta interfaz es la basado en texto, un [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) estructura.

## <a name="requirements"></a>Requisitos
 Encabezado: msdbg.h

 Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [Interfaces básicas](../../../extensibility/debugger/reference/core-interfaces.md)
- [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md)
- [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)
- [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)