---
title: 'IDebugSymbolProvider:: GetAddressesFromContext | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugSymbolProvider::GetAddressesFromContext
helpviewer_keywords:
- IDebugSymbolProvider::GetAddressesFromContext method
ms.assetid: a3124883-a255-4543-a5ec-e1c7a97beb69
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 7cf7599cf0fc37c16467c29c2b432f1f58b172fe
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80719432"
---
# <a name="idebugsymbolprovidergetaddressesfromcontext"></a>IDebugSymbolProvider::GetAddressesFromContext
Este método asigna un contexto de documento en una matriz de direcciones de depuración.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetAddressesFromContext( 
   IDebugDocumentContext2* pDocContext,
   BOOL                    fStatmentOnly,
   IEnumDebugAddresses**   ppEnumBegAddresses,
   IEnumDebugAddresses**   ppEnumEndAddresses
);
```

```csharp
int GetAddressesFromContext(
   IDebugDocumentContext2  pDocContext,
   bool                    fStatmentOnly,
   out IEnumDebugAddresses ppEnumBegAddresses,
   out IEnumDebugAddresses ppEnumEndAddresses
);
```

## <a name="parameters"></a>Parámetros
`pDocContext`\
de Contexto del documento.

`fStatmentOnly`\
de Si es TRUE, limita las direcciones de depuración a una única instrucción.

`ppEnumBegAddresses`\
enuncia Devuelve un enumerador para las direcciones de depuración de inicio asociadas a esta instrucción o línea.

`ppEnumEndAddresses`\
enuncia Devuelve un enumerador [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md) para las direcciones de depuración finales asociadas a esta instrucción o línea.

## <a name="return-value"></a>Valor devuelto
 Si la operación se realiza correctamente, devuelve `S_OK`; de lo contrario, devuelve un código de error.

## <a name="remarks"></a>Observaciones
 Un contexto de documento suele indicar un intervalo de líneas de código fuente. Este método proporciona las direcciones de depuración inicial y final asociadas a estas líneas. Algunos lenguajes admiten instrucciones que abarcan varias líneas o líneas que contienen más de una instrucción. Este método proporciona una marca para limitar las direcciones de depuración a una única instrucción.

 Es posible que una sola instrucción tenga varias direcciones de depuración, como en el caso de las plantillas.

## <a name="see-also"></a>Vea también
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)
- [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)
- [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)
