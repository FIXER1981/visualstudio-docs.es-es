---
title: IDebugDocument2::GetName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocument2::GetName
helpviewer_keywords:
- IDebugDocument2::GetName
ms.assetid: 6f09ff09-b0cf-4472-8fc8-143991f0ceb1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1e653f7f735be43f2edeb4bd3c7935d3c89a9e58
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2019
ms.locfileid: "66204746"
---
# <a name="idebugdocument2getname"></a>IDebugDocument2::GetName
Obtiene el nombre del documento en una de varias formas.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetName( 
   GETNAME_TYPE gnType,
   BSTR*        pbstrFileName
);
```

```csharp
int GetName( 
   enum_GETNAME_TYPE gnType,
   out string        pbstrFileName
);
```

## <a name="parameters"></a>Parámetros
`gnType`\
[in] Un valor de la [GETNAME_TYPE](../../../extensibility/debugger/reference/getname-type.md) enumeración que determina el tipo de nombre para devolver.

`pbstrFileName`\
[out] Devuelve una cadena que contiene el nombre del documento.

## <a name="return-value"></a>Valor devuelto
 Si es correcto, devuelve `S_OK`; en caso contrario, devuelve un código de error.

## <a name="remarks"></a>Comentarios
 Este método, por ejemplo, puede devolver el nombre del documento como un título o como un nombre de archivo o incluso parte de un nombre de archivo.

## <a name="see-also"></a>Vea también
- [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)
- [GETNAME_TYPE](../../../extensibility/debugger/reference/getname-type.md)