---
title: IDebugSymbolProvider::GetAddressesFromContext | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugSymbolProvider::GetAddressesFromContext
helpviewer_keywords:
- IDebugSymbolProvider::GetAddressesFromContext method
ms.assetid: a3124883-a255-4543-a5ec-e1c7a97beb69
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a7b28010f117b1bb6616250f1e188bd5acb38cda
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56692559"
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

#### <a name="parameters"></a>Parámetros
 `pDocContext`

 [in] El contexto del documento.

 `fStatmentOnly`

 [in] Si es TRUE, limita las direcciones de depuración para una sola instrucción.

 `ppEnumBegAddresses`

 [out] Devuelve un enumerador para las direcciones iniciales de depuración asociados con esta instrucción o línea.

 `ppEnumEndAddresses`

 [out] Devuelve un [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md) enumerador para las direcciones de depuración final asociado a esta instrucción o línea.

## <a name="return-value"></a>Valor devuelto
 Si es correcto, devuelve `S_OK`; en caso contrario, devuelve un código de error.

## <a name="remarks"></a>Comentarios
 Un contexto de documento normalmente indica un intervalo de líneas de código fuente. Este método proporciona la fecha inicial y final de las direcciones de depuración asociadas con estas líneas. Algunos lenguajes permiten que las instrucciones que abarcan varias líneas, o líneas que contiene más de una instrucción. Este método proporciona una marca para limitar las direcciones de depuración para una sola instrucción.

 Es posible que una sola instrucción tener varias direcciones de depuración, como en el caso de plantillas.

## <a name="see-also"></a>Vea también
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)
- [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)
- [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)