---
title: IEnumDebugPorts2::Skip | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugPorts2::Skip
helpviewer_keywords:
- IEnumDebugPorts2::Skip
ms.assetid: a837383f-7b39-4e06-b336-f1715b073dbe
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 56d941a826287f119fefdd11d305359dba02078d
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56681782"
---
# <a name="ienumdebugports2skip"></a>IEnumDebugPorts2::Skip
Omite el número especificado de elementos.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT Skip(
   ULONG celt
);
```

```csharp
int Skip(
   uint celt
);
```

#### <a name="parameters"></a>Parámetros
 `celt`

 [in] Número de elementos que se van a omitir.

## <a name="return-value"></a>Valor devuelto
 Si la operación se realiza correctamente, devuelve `S_OK`. Devuelve `S_FALSE` si `celt` es mayor que el número de elementos restantes; en caso contrario, devuelve un código de error.

## <a name="remarks"></a>Comentarios
 Si `celt` especifica un valor mayor que el número de elementos restantes, la enumeración se establece en el extremo y `S_FALSE` se devuelve.

## <a name="see-also"></a>Vea también
- [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)