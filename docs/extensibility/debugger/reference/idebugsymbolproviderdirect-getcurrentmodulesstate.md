---
title: IDebugSymbolProviderDirect::GetCurrentModulesState | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- GetCurrentModulesState
- IDebugSymbolProviderDirect::GetCurrentModulesState
ms.assetid: a0c85318-5686-4eed-b213-21f2b9e681e6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a2a4cfb78c7ccf24a79c5326f7f263a1b78302a3
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56699995"
---
# <a name="idebugsymbolproviderdirectgetcurrentmodulesstate"></a>IDebugSymbolProviderDirect::GetCurrentModulesState
Recupera información sobre el grupo de símbolos de los cuales el proveedor de símbolos es un miembro.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetCurrentModulesState(
    DWORD*          pState,
    unsigned long * count
);
```

```csharp
int GetCurrentModulesState(
    out uint pState,
    out uint count
);
```

#### <a name="parameters"></a>Parámetros
 `pState`

 [out] El estado del grupo del proveedor de símbolos.

 `count`

 [out] Número de módulos en el grupo.

## <a name="return-value"></a>Valor devuelto
 Si es correcto, devuelve `S_OK`; en caso contrario, devuelve un código de error.

## <a name="remarks"></a>Comentarios
 El estado cambia cada vez que un módulo se agrega o quita, el grupo de símbolos. Por lo tanto, este método puede utilizarse para detectar si se ha modificado un grupo de símbolos.

## <a name="see-also"></a>Vea también
- [IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)