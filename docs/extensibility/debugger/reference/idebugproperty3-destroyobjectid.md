---
title: IDebugProperty3::DestroyObjectID | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty3::DestroyObjectID
helpviewer_keywords:
- IDebugProperty3::DestroyObjectID
ms.assetid: bd08f356-cc67-4717-98c9-c3d00cad2040
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: c117cab17340f50a1ed580d081c3291308ec0d9d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "66308885"
---
# <a name="idebugproperty3destroyobjectid"></a>IDebugProperty3::DestroyObjectID
Destruye el identificador único asociado a esta propiedad, que indica que el llamador ya no se ocupa de identificar esta propiedad de forma única en todas las demás propiedades.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT DestroyObjectID(
   void
);
```

```csharp
int DestroyObjectID();
```

## <a name="return-value"></a>Valor devuelto
 Si es correcto, devuelve `S_OK`; en caso contrario, devuelve un código de error.

## <a name="remarks"></a>Comentarios
 Si el motor de depuración no es necesario admitir los identificadores únicos para una propiedad (debido a ya realiza un seguimiento de ellos inequívocamente internamente), a continuación, puede devolver simplemente `E_NOTIMPL` para este método.

 Los identificadores únicos se crean con una llamada a la [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md) método cuando el llamador desea asegurarse de que esta propiedad se identifica entre todas las demás propiedades.

## <a name="see-also"></a>Vea también
- [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)
- [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)