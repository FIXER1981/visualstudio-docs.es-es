---
title: IDiaPropertyStorage::ReadLONG | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadLONG
ms.assetid: 32054cbc-db55-4513-a1b4-de80e77aac8a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2fb277368e23cf51a4d3d3b69226ee6bf093d6c3
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56615577"
---
# <a name="idiapropertystoragereadlong"></a>IDiaPropertyStorage::ReadLONG
Lee `LONG` valores en un conjunto de propiedades.

## <a name="syntax"></a>Sintaxis

```C++
HRESULT ReadDLONG ( 
   PROPID id,
   LONG*  pValue
);
```

#### <a name="parameters"></a>Parámetros
 `id`

[in] Identificador de la propiedad de lectura (`PROPID` se define en el archivo WTypes.h como un `ULONG`).

 `pValue`

[out] Devuelve el valor de propiedad.

## <a name="return-value"></a>Valor devuelto
 Si es correcto, devuelve `S_OK`; en caso contrario, devuelve un código de error. Devuelve `E_INVALIDARG` si la propiedad no es de tipo `LONG`.

## <a name="remarks"></a>Comentarios
 Un `LONG` se define por Windows como un entero de 32 bits con signo.

## <a name="see-also"></a>Vea también
- [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)