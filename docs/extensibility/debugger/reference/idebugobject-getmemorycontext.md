---
title: 'IDebugObject:: GetMemoryContext | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject::GetMemoryContext
helpviewer_keywords:
- IDebugObject::GetMemoryContext method
ms.assetid: 6760a0d3-a898-4e81-b68f-c45c584b225b
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 16427685765c1471fba3993743efc204cb99c367
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80726657"
---
# <a name="idebugobjectgetmemorycontext"></a>IDebugObject::GetMemoryContext
Obtiene el contexto de memoria que representa la dirección del valor del objeto.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetMemoryContext( 
   IDebugMemoryContext2** pContext
);
```

```csharp
int GetMemoryContext(
   ref IDebugMemoryContext2 pContext
);
```

## <a name="parameters"></a>Parámetros
`pContext`\
enuncia Devuelve un objeto [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) que representa la dirección del valor del objeto.

## <a name="return-value"></a>Valor devuelto
 Si se realiza correctamente, Devuelve S_OK; de lo contrario, devuelve un código de error.

## <a name="remarks"></a>Observaciones
 El contexto de memoria devuelto especifica la dirección del valor representado por este objeto [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) .

## <a name="see-also"></a>Vea también
- [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)
