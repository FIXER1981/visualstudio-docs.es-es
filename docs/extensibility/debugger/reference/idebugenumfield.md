---
title: IDebugEnumField | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEnumField
helpviewer_keywords:
- IDebugEnumField interface
ms.assetid: 42f685bf-0f39-47f4-98b0-6022efe2bf97
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4e2bcb8f8562b5b20231879d46c64eb73af027f0
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56680001"
---
# <a name="idebugenumfield"></a>IDebugEnumField
Esta interfaz representa un tipo de enumeración.

## <a name="syntax"></a>Sintaxis

```
IDebugEnumField : IDebugContainerField
```

## <a name="notes-for-implementers"></a>Notas para los implementadores
 Un proveedor de símbolos implementa esta interfaz para representar una enumeración.

## <a name="notes-for-callers"></a>Notas para los llamadores
 Use [QueryInterface](/cpp/atl/queryinterface) para obtener esta interfaz desde el [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) interfaz si [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) devuelve `FIELD_TYPE_ENUM`.

## <a name="methods-in-vtable-order"></a>Métodos en orden de VTable
 Además de los métodos en el `IDebugField` y `IDebugContainerField` interfaces, esta interfaz implementa los métodos siguientes:

|Método|Descripción|
|------------|-----------------|
|[GetUnderlyingSymbol](../../../extensibility/debugger/reference/idebugenumfield-getunderlyingsymbol.md)|Devuelve un [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) que describe el nombre para este tipo de enumeración.|
|[GetStringFromValue](../../../extensibility/debugger/reference/idebugenumfield-getstringfromvalue.md)|Devuelve el nombre de la constante de enumeración asociada con el valor especificado.|
|[GetValueFromString](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstring.md)|Devuelve el valor asociado con el nombre de constante de enumeración determinado|
|[GetValueFromStringCaseInsensitive](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstringcaseinsensitive.md)|Devuelve el valor asociado con el nombre de constante de enumeración especificado pero el caso y pasa por alto.|

## <a name="remarks"></a>Comentarios
 Es el símbolo subyacente que realmente está enlazado a una ubicación con [enlazar](../../../extensibility/debugger/reference/idebugbinder-bind.md).

## <a name="requirements"></a>Requisitos
 Encabezado: sh.h

 Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [Interfaces de proveedor de símbolos](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [Bind](../../../extensibility/debugger/reference/idebugbinder-bind.md)