---
title: IDiaEnumSegments::Clone | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSegments::Clone method
ms.assetid: 93deaac6-72ab-4408-ba14-66174a618757
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9992b17155601284387981a9b424a77d3d9b5580
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56616617"
---
# <a name="idiaenumsegmentsclone"></a>IDiaEnumSegments::Clone
Crea un enumerador que contiene el mismo estado de enumeración que el enumerador actual.

## <a name="syntax"></a>Sintaxis

```C++
HRESULT Clone ( 
   IDiaEnumSegments** ppenum
);
```

#### <a name="parameters"></a>Parámetros
 ppenum

[out] Devuelve un [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md) objeto que contiene un duplicado del enumerador. No se duplican los segmentos, solo el enumerador.

## <a name="return-value"></a>Valor devuelto
 Si es correcto, devuelve `S_OK`; en caso contrario, devuelve un código de error.

## <a name="see-also"></a>Vea también
- [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)