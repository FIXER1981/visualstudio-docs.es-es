---
title: IDebugCustomAttribute::GetAttributeTypeField | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCustomAttribute::GetAttributeTypeField
helpviewer_keywords:
- IDebugCustomAttribute::GetAttributeTypeField
ms.assetid: d6ce26d5-42ba-44c1-8659-0516db5bc82d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cbbf0d91b344f1a45eb09d480eb631ac1a159046
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56722790"
---
# <a name="idebugcustomattributegetattributetypefield"></a>IDebugCustomAttribute::GetAttributeTypeField
Obtiene el tipo de clase de atributo personalizado.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetAttributeTypeField( 
   IDebugClassField** ppCAType
);
```

```csharp
int GetAttributeTypeField(
   out IDebugClassField ppCAType
);
```

#### <a name="parameters"></a>Parámetros
 `ppCAType`

 [out] Devuelve el [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) objeto que representa la clase de los cuales el atributo personalizado es una instancia.

## <a name="return-value"></a>Valor devuelto
 Si se realiza correctamente, devuelve S_OK; en caso contrario, devuelve un código de error.

## <a name="remarks"></a>Comentarios
 Un atributo personalizado siempre es una clase. Este método proporciona acceso a un [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) objeto que describe esa clase.

## <a name="see-also"></a>Vea también
- [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)