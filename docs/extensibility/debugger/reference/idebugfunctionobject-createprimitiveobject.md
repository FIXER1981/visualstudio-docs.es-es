---
title: IDebugFunctionObject::CreatePrimitiveObject | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugFunctionObject::CreatePrimitiveObject
helpviewer_keywords:
- IDebugFunctionObject::CreatePrimitiveObject method
ms.assetid: 6e9dc8b6-b4e1-4abf-b6e0-e885910775bc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 185466d8bb89b504d7b6f8df4b624390205d3944
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56685292"
---
# <a name="idebugfunctionobjectcreateprimitiveobject"></a>IDebugFunctionObject::CreatePrimitiveObject
Crea un objeto de datos primitivos, como un número entero simple.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT CreatePrimitiveObject( 
   OBJECT_TYPE    ot,
   IDebugObject** ppObject
);
```

```csharp
int CreatePrimitiveObject(
   enum_OBJECT_TYPE ot,
   out IDebugObject ppObject
);
```

#### <a name="parameters"></a>Parámetros
 `ot`

 [in] Un valor de la [OBJECT_TYPE](../../../extensibility/debugger/reference/object-type.md) enumeración que representa el tipo de primitiva a crear.

 `ppObject`

 [out] Devuelve un [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) que representa el objeto recién creado.

## <a name="return-value"></a>Valor devuelto
 Si se realiza correctamente, devuelve S_OK; en caso contrario, devuelve un código de error.

## <a name="remarks"></a>Comentarios
 Llame a este método para crear un objeto que representa un objeto primitivo que es un parámetro a la función representada por el [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) interfaz. Por ejemplo, si la cadena de expresión es "myString(5)", este método se usaría para crear un objeto que representa el entero 5.

## <a name="see-also"></a>Vea también
- [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)