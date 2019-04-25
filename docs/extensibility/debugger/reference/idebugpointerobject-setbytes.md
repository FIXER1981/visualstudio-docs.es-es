---
title: IDebugPointerObject::SetBytes | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPointerObject::SetBytes
helpviewer_keywords:
- IDebugPointerObject::SetBytes method
ms.assetid: 8c578b38-38d7-46f3-bb2e-8a730fccd334
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e54a7f38eed85ffe2757b373de1af59e1aaa126b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56694732"
---
# <a name="idebugpointerobjectsetbytes"></a>IDebugPointerObject::SetBytes
Establece el valor señalado por una serie de bytes consecutivos.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT SetBytes( 
   DWORD  dwStart,
   DWORD  dwCount,
   BYTE*  pBytes,
   DWORD* pdwBytes
);
```

```csharp
int SetBytes(
   uint     dwStart,
   uint     dwCount,
   byte[]   pBytes,
   out uint pdwBytes
);
```

#### <a name="parameters"></a>Parámetros
 `dwStart`

 [in] Posición de desplazamiento, en bytes, desde el principio del objeto que apunta.

 `dwCount`

 [in] El número de bytes para establecer.

 `pBytes`

 [in] Una matriz de bytes que representa el nuevo valor. Este valor se almacena en el objeto, comenzando en el desplazamiento dado.

 `pdwBytes`

 [out] Devuelve que el número de bytes establecido realmente.

## <a name="return-value"></a>Valor devuelto
 Si se realiza correctamente, devuelve S_OK; en caso contrario, devuelve un código de error.

## <a name="remarks"></a>Comentarios
 Este método se utiliza si el puntero, tal como está representada por este [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md) apunta a un tipo primitivo o una matriz de tipos primitivos (es decir, una matriz que puede representarse mediante una sencilla secuencia de bytes). Esto `IDebugPointerObject` objeto no puede ser una referencia nula (debe apuntar a una dirección de memoria).

## <a name="see-also"></a>Vea también
- [GetBytes](../../../extensibility/debugger/reference/idebugpointerobject-getbytes.md)
- [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)