---
title: IDiaSymbol::get_isHotpatchable | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isHotpatchable method
ms.assetid: b7b6f490-1cf2-4a68-9237-b152dac84d3c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 27218a2814e14e0a1ec30bd7fb4dc4840589251c
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72740229"
---
# <a name="idiasymbolget_ishotpatchable"></a>IDiaSymbol::get_isHotpatchable
Recupera una marca que indica si el módulo se compiló con el modificador de compilador [/hotpatch (crear imagen una)](/cpp/build/reference/hotpatch-create-hotpatchable-image) .

## <a name="syntax"></a>Sintaxis

```C++
HRESULT get_isHotpatchable(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>Parámetros
 `pFlag`

enuncia Devuelve `TRUE` si el módulo es revisable en caliente; de lo contrario, devuelve `FALSE`.

## <a name="return-value"></a>Valor devuelto
 Si se realiza correctamente, devuelve `S_OK`; de lo contrario, devuelve `S_FALSE` o el código de error.

> [!NOTE]
> Un valor devuelto de `S_FALSE` significa que la propiedad no está disponible para el símbolo.

## <a name="remarks"></a>Comentarios
 Esta propiedad está disponible en el tipo de símbolo `SymTagCompilandDetails` (vea [CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md)).

## <a name="requirements"></a>Requisitos

|Requisito|Descripción|
|-----------------|-----------------|
|Encabezado:|dia2.h|
|Versión:|SDK de DIA v 8.0|

## <a name="see-also"></a>Vea también
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md)