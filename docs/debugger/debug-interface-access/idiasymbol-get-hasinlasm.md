---
title: IDiaSymbol::get_hasInlAsm | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_hasInlAsm method
ms.assetid: 7001c7cc-1459-4929-851b-a08066a803c6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a62126b7e752c8d09a32891e8886be0df07b8d12
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56606345"
---
# <a name="idiasymbolgethasinlasm"></a>IDiaSymbol::get_hasInlAsm
Recupera una marca que especifica si la función contiene un ensamblado alineado.

## <a name="syntax"></a>Sintaxis

```C++
HRESULT get_hasInlAsm(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>Parámetros
 `pFlag`

[out] Devuelve `TRUE` si la función no tiene ningún ensamblado insertado; en caso contrario, devuelve `FALSE`.

## <a name="return-value"></a>Valor devuelto
 Si es correcto, devuelve `S_OK`; en caso contrario, devuelve `S_FALSE` o un código de error.

> [!NOTE]
>  Un valor devuelto de `S_FALSE` significa que la propiedad no está disponible para el símbolo.

## <a name="requirements"></a>Requisitos

|Requisito|Descripción|
|-----------------|-----------------|
|Encabezado:|dia2.h|
|Versión:|SDK de DIA v8.0|

## <a name="see-also"></a>Vea también
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)