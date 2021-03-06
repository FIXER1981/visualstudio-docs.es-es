---
title: 'IDebugFunctionObject:: CreateArrayObject | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugFunctionObject::CreateArrayObject
helpviewer_keywords:
- IDebugFunctionObject::CreateArrayObject method
ms.assetid: a380e53c-15f1-401f-927f-f366eea789e6
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: bd4c07f2b95ff3077de79d4bc63f4fad19b0c6fa
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80728606"
---
# <a name="idebugfunctionobjectcreatearrayobject"></a>IDebugFunctionObject::CreateArrayObject
Crea un objeto de matriz. Esta matriz puede contener valores primitivos o de instancia de objeto.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT CreateArrayObject( 
   OBJECT_TYPE    ot,
   IDebugField*   pClassField,
   DWORD          dwRank,
   DWORD          dwDims[],
   DWORD          dwLowBounds[],
   IDebugObject** ppObject
);
```

```csharp
int CreateArrayObject(
   enum_OBJECT_TYPE ot,
   IDebugField      pClassField,
   uint             dwRank,
   uint[]           dwDims,
   uint[]           dwLowBounds,
   out IDebugObject ppObject
);
```

## <a name="parameters"></a>Parámetros
`ot`\
de Especifica un valor de la enumeración [OBJECT_TYPE](../../../extensibility/debugger/reference/object-type.md) que indica el tipo del nuevo objeto de matriz.

`pClassField`\
de Un objeto [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) que representa la clase de un objeto, si se crea una matriz de valores de instancia de objeto. Si crea una matriz de objetos primitivos, este parámetro es un valor nulo.

`dwRank`\
de El rango o el número de dimensiones de la matriz.

`dwDims`\
de Los tamaños de cada dimensión de la matriz.

`dwLowBounds`\
de El origen de cada dimensión (normalmente 0 o 1).

`ppObject`\
enuncia Devuelve un objeto [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) que representa la matriz recién creada. En realidad, se trata de un objeto [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md) .

## <a name="return-value"></a>Valor devuelto
 Si se realiza correctamente, Devuelve S_OK; de lo contrario, devuelve un código de error.

## <a name="remarks"></a>Observaciones
 Llame a este método para crear un objeto que represente un parámetro de matriz a la función representada por la interfaz [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) .

## <a name="see-also"></a>Vea también
- [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)
