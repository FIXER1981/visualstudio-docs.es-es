---
title: IDebugModule2::GetInfo | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModule2::GetInfo
helpviewer_keywords:
- GetInfo method
- IDebugModule2::GetInfo method
ms.assetid: de337e66-294f-4ac9-b21e-71fac7418e36
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a0a5ad3d7651e89c2ef864a184155e8b0a430d79
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56694808"
---
# <a name="idebugmodule2getinfo"></a>IDebugModule2::GetInfo
Obtiene información sobre este módulo.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetInfo( 
   MODULE_INFO_FIELDS dwFields,
   MODULE_INFO*       pInfo
);
```

```cpp
int GetInfo( 
   enum_MODULE_INFO_FIELDS dwFields,
   MODULE_INFO[]           pInfo
);
```

#### <a name="parameters"></a>Parámetros
 `dwFields`

 [in] Una combinación de marcas de la [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md) enumeración que especifican qué campos de `pInfo` son para rellenarlo.

 `pInfo`

 [in, out] Un [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) estructura que se rellena con una descripción del módulo.

## <a name="return-value"></a>Valor devuelto
 Si es correcto, devuelve `S_OK`; en caso contrario, devuelve un código de error.

## <a name="remarks"></a>Comentarios
 El [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) estructura contiene el nombre del módulo que se muestra en el **módulos** ventana.

## <a name="see-also"></a>Vea también
- [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)
- [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)
- [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)