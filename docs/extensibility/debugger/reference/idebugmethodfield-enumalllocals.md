---
title: 'IDebugMethodField:: EnumAllLocals | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMethodField::EnumAllLocals
helpviewer_keywords:
- IDebugMethodField::EnumAllLocals method
ms.assetid: 0bc7cc13-2628-4bd8-8c06-4d2aa6755ea8
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 50da5af616c56276a0299a0d08e6eeb0b88181cc
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80727333"
---
# <a name="idebugmethodfieldenumalllocals"></a>IDebugMethodField::EnumAllLocals
Crea un enumerador para todas las variables locales del método, incluidos los generados internamente por un compilador.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT EnumAllLocals( 
   IDebugAddress*     pAddress,
   IEnumDebugFields** ppLocals
);
```

```csharp
int EnumAllLocals(
   IDebugAddress        pAddress,
   out IEnumDebugFields ppLocals
);
```

## <a name="parameters"></a>Parámetros
`pAddress`\
de Un objeto [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) que representa una dirección de depuración dentro del método, que apunta a un ámbito o contexto determinado.

`ppLocals`\
enuncia Devuelve un objeto [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) que representa la lista de todas las variables locales del ámbito especificado; de lo contrario, devuelve un valor null que indica que no hay variables locales.

## <a name="return-value"></a>Valor devuelto
 Si es correcto, Devuelve S_OK o devuelve S_FALSE si no hay variables locales. De lo contrario, devuelve un código de error.

## <a name="remarks"></a>Observaciones
 Solo se enumeran las variables definidas dentro del bloque que contiene la dirección de depuración especificada. Este método incluye cualquier variables locales generadas por el compilador. Si lo único que se necesita son las variables locales definidas explícitamente en el origen, llame al método [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md) .

 Un método puede contener varios contextos de ámbito o bloques.

## <a name="see-also"></a>Vea también
- [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)
- [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)
