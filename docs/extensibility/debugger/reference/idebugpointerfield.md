---
title: IDebugPointerField | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPointerField
helpviewer_keywords:
- IDebugPointerField interface
ms.assetid: d51bd5b2-f18e-4e27-b4fb-e6f652fbf635
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: dc6939296fa2bfa59aad1824529f8b708a4cd5cb
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "66308860"
---
# <a name="idebugpointerfield"></a>IDebugPointerField
Esta interfaz representa un tipo de puntero.

## <a name="syntax"></a>Sintaxis

```
IDebugPointerField : IDebugContainerField
```

## <a name="notes-for-implementers"></a>Notas para los implementadores
 El proveedor de símbolos implementa esta interfaz para representar un puntero.

## <a name="notes-for-callers"></a>Notas para los llamadores
 Use [QueryInterface](/cpp/atl/queryinterface) para obtener esta interfaz desde el [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) interfaz si [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) devuelve `FIELD_TYPE_POINTER`.

## <a name="methods-in-vtable-order"></a>Métodos en orden de Vtable
 Además de los métodos en el `IDebugField` y `IDebugContainerField` interfaces, esta interfaz se implementa el método siguiente:

|Método|Descripción|
|------------|-----------------|
|[GetDereferencedField](../../../extensibility/debugger/reference/idebugpointerfield-getdereferencedfield.md)|Devuelve un [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) que describe el destino del puntero.|

## <a name="remarks"></a>Comentarios
 En C/C ++, un puntero puede ser un contenedor si se usa con la notación de matriz. Por ejemplo, dada `char *pString`, `pString` tiene un tipo de puntero a `char`. `pString[3]` tiene el tipo de un contenedor que es un puntero a `char` que hace referencia al cuarto elemento de ese contenedor.

## <a name="requirements"></a>Requisitos
 Encabezado: sh.h

 Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [Interfaces de proveedor de símbolos](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)