---
title: IDebugEngine2::RemoveSetException | Documentos de Microsoft
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine2::RemoveSetException
helpviewer_keywords:
- IDebugEngine2::RemoveSetException
ms.assetid: bdd25097-0e9d-4218-b417-0497ea48d2e8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2d4e8e919f69736025eb211dfd46ee72f461839d
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56679377"
---
# <a name="idebugengine2removesetexception"></a>IDebugEngine2::RemoveSetException
Borra la excepción especificada para que ya no es controlada por el motor de depuración.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT RemoveSetException( 
   EXCEPTION_INFO* pException
);
```

```csharp
int RemoveSetException( 
   EXCEPTION_INFO[] pException
);
```

#### <a name="parameters"></a>Parámetros
 `pException`

 [in] Un [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) estructura que describe la excepción que se va a quitar.

## <a name="return-value"></a>Valor devuelto
 Si es correcto, devuelve `S_OK`; en caso contrario, devuelve un código de error.

## <a name="remarks"></a>Comentarios
 La excepción que se va a quitar debe ha establecido previamente mediante una llamada anterior a la [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md) método.

 Para quitar todas las excepciones de conjunto a la vez, llame a la [RemoveAllSetExceptions](../../../extensibility/debugger/reference/idebugengine2-removeallsetexceptions.md) método.

## <a name="see-also"></a>Vea también
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
- [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)