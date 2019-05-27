---
title: IEEVisualizerDataProvider::SetObjectForVisualizer | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEEVisualizerDataProvider::SetObjectForVisualizer
helpviewer_keywords:
- IEEVisualizerDataProvider::SetObjectForVisualizer method
ms.assetid: 40dad2be-57ff-4f74-9d82-c48039c125c4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 31bc89e248d609e8b828d4cc5b9ac41c8e15c70c
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2019
ms.locfileid: "66203702"
---
# <a name="ieevisualizerdataprovidersetobjectforvisualizer"></a>IEEVisualizerDataProvider::SetObjectForVisualizer
Este método cambia el objeto que representa el visualizador.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT SetObjectForVisualizer(
   IDebugObject*  pNewObject,
   BSTR*          error,
   IDebugObject** pException
);
```

```csharp
int SetObjectForVisualizer(
   IDebugObject     pNewObject,
   out string       error,
   out IDebugObject pException
);
```

## <a name="parameters"></a>Parámetros
`pNewObject`\
[in] El objeto va a establecer.

`error`\
[out] Si se produjo un error al configurar el objeto, esta cadena contiene el mensaje de error.

`pException`\
[out] Si se produjo un error, este objeto contiene la información de excepción.

## <a name="return-value"></a>Valor devuelto
 Si es correcto, devuelve `S_OK`; en caso contrario, devuelve un código de error.

## <a name="remarks"></a>Comentarios
 Es responsabilidad del implementador para determinar cómo se devuelve información de error. Sin embargo, es posible que algunos autores de llamadas, es posible que solo se ha producido un error, compruebe si se devolvió un objeto de excepción para que sepan que hay por lo que este método siempre debe devolver un objeto de excepción si se produjo un error. También se debe proporcionar la cadena de error en caso de que el llamador desea hacer uso de ella.

## <a name="see-also"></a>Vea también
- [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)