---
title: IDebugPointerObject::GetBytes | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPointerObject::GetBytes
helpviewer_keywords:
- IDebugPointerObject::GetBytes method
ms.assetid: e986c188-87fb-4b51-86e9-ee6a0035bdab
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7a2c93e032175ce556d5504ed8b3f57dcf619a61
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56677635"
---
# <a name="idebugpointerobjectgetbytes"></a>IDebugPointerObject::GetBytes
Obtiene el valor señalado como una serie de bytes consecutivos.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetBytes( 
   DWORD  dwStart,
   DWORD  dwCount,
   BYTE*  pBytes,
   DWORD* pdwBytes
);
```

```csharp
int GetBytes(
   uint       dwStart,
   uint       dwCount,
   out byte[] pBytes,
   out uint   pdwBytes
);
```

#### <a name="parameters"></a>Parámetros
 `dwStart`

 [in] Posición de desplazamiento, en bytes, desde el principio del objeto que apunta.

 `dwCount`

 [in] El número de bytes para recuperar.

 `pBytes`

 [in, out] Una matriz que se rellena con el valor como una serie de bytes consecutivos, comenzando en el desplazamiento especificado desde el objeto señalado.

 `pdwBytes`

 [out] Devuelve el número de bytes que se recuperan realmente.

## <a name="return-value"></a>Valor devuelto
 Si se realiza correctamente, devuelve S_OK; en caso contrario, devuelve un código de error.

## <a name="remarks"></a>Comentarios
 Este método se utiliza si el puntero, tal como está representada por este [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md) apunta a un tipo primitivo o una matriz de tipos primitivos (es decir, una matriz que puede representarse mediante una sencilla secuencia de bytes).

## <a name="see-also"></a>Vea también
- [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)
- [SetBytes](../../../extensibility/debugger/reference/idebugpointerobject-setbytes.md)