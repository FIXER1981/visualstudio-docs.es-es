---
title: IEnumDebugFields | Documentos de Microsoft
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugFields
helpviewer_keywords:
- IEnumDebugFields interface
ms.assetid: 403c2a51-3ba5-431f-a1dd-2f3b2046c00c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9f557b722a36665b20f5e06093027f8085a014ed
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56716758"
---
# <a name="ienumdebugfields"></a>IEnumDebugFields
Esta interfaz representa una colección de objetos que implementan la [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) interfaz.

## <a name="syntax"></a>Sintaxis

```
IEnumDebugFields : IUnknown
```

## <a name="notes-for-implementers"></a>Notas para los implementadores
 Esta interfaz se implementa mediante el proveedor de símbolos para ofrecer conjuntos de objetos que implementan la [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) interfaz. Tenga en cuenta que esto no es una enumeración de COM estándar debido a la presencia de la [GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md) método.

## <a name="notes-for-callers"></a>Notas para los llamadores
 Esta interfaz es devuelto por [GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md) y [GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md).

## <a name="methods-in-vtable-order"></a>Métodos en orden de Vtable
 Esta interfaz implementa los métodos siguientes.

|Método|Descripción|
|------------|-----------------|
|[Siguiente](../../../extensibility/debugger/reference/ienumdebugfields-next.md)|Recupera el siguiente conjunto de [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objetos de la enumeración.|
|[Skip](../../../extensibility/debugger/reference/ienumdebugfields-skip.md)|Omite un número especificado de entradas.|
|[Reset](../../../extensibility/debugger/reference/ienumdebugfields-reset.md)|Restablece la enumeración a la primera entrada.|
|[Clone](../../../extensibility/debugger/reference/ienumdebugfields-clone.md)|Recupera una copia de la enumeración actual.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md)|Recupera el número de entradas de la enumeración.|

## <a name="remarks"></a>Comentarios

## <a name="requirements"></a>Requisitos
 Encabezado: sh.h

 Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [Interfaces de proveedor de símbolos](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)
- [GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)