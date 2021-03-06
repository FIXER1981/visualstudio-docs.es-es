---
title: 'IDebugObject:: GetManagedDebugObject | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject::GetManagedDebugObject
helpviewer_keywords:
- IDebugObject::GetManagedDebugObject method
ms.assetid: cb89692e-7657-47ff-846d-311943521951
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 67d0d7a8642c9dd90067b0e197f420d4cc821faa
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80726690"
---
# <a name="idebugobjectgetmanageddebugobject"></a>IDebugObject::GetManagedDebugObject
Crea una copia del objeto administrado en el espacio de direcciones del motor de depuración.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetManagedDebugObject( 
   IDebugManagedObject** ppObject
);
```

```csharp
int GetManagedDebugObject(
   out IDebugManagedObject ppObject
);
```

## <a name="parameters"></a>Parámetros
`ppObject`\
enuncia Devuelve un objeto [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md) que representa el objeto administrado que se acaba de crear.

## <a name="return-value"></a>Valor devuelto
 Si se realiza correctamente, Devuelve S_OK; de lo contrario, devuelve un código de error. Devuelve E_FAIL si este [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) no representa una instancia de clase de valor administrado.

## <a name="remarks"></a>Observaciones
 Este objeto [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) debe representar una instancia de clase de valor administrado, como una `System.Decimal` instancia de. Al tener una copia local, se elimina la sobrecarga que supone llamar a [Evaluate](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md) .

## <a name="see-also"></a>Vea también
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
- [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)
