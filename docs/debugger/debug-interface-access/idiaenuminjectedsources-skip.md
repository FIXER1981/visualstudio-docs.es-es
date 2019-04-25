---
title: IDiaEnumInjectedSources::Skip | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumInjectedSources::Skip method
ms.assetid: 4aad6a51-f2d3-4064-b216-60d830d0a560
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 807ed82a68089cb656f68c8cc1881dce683bb8a9
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56640147"
---
# <a name="idiaenuminjectedsourcesskip"></a>IDiaEnumInjectedSources::Skip
Omite un número especificado de orígenes insertados en una secuencia de enumeración.

## <a name="syntax"></a>Sintaxis

```C++
HRESULT Skip ( 
   ULONG celt
);
```

#### <a name="parameters"></a>Parámetros
 celt

[in] El número de orígenes insertados en la secuencia de enumeración que se omitirán.

## <a name="return-value"></a>Valor devuelto
 Si es correcto, devuelve `S_OK`; en caso contrario, devuelve `S_FALSE` si hay insertados no hay más orígenes para omitir.

## <a name="see-also"></a>Vea también
- [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)