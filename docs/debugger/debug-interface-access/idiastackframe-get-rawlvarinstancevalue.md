---
title: IDiaStackFrame::get_rawLVarInstanceValue | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_rawLVarInstanceValue method
ms.assetid: ce526259-85a6-475b-9274-0b3a21d95db2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a8ad236307360a96f64999313764424305980fc9
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56624027"
---
# <a name="idiastackframegetrawlvarinstancevalue"></a>IDiaStackFrame::get_rawLVarInstanceValue
Este método recupera el valor de la variable local indicada como bytes sin formato.

## <a name="syntax"></a>Sintaxis

```C++
HRESULT get_rawLVarInstanceValue(
   IDiaLVarInstance* pInstance,
   DWORD             cbDataMax,
   DWORD*            pcbData,
   BYTE*             pbData
);
```

#### <a name="parameters"></a>Parámetros
 `pInstance`

[in] Un `IDiaLVarInstance` que representa una instancia de la variable local para obtener el valor para el objeto.

 `cbDataMax`

[in] Número máximo de bytes en el búfer señalado por `pbData`. Esto puede tener un máximo de 8 bytes (`sizeof(ULONGLONG)`).

 `pcbData`

[out] Devuelve el número real de bytes almacenados en el búfer.

 `pbData`

[out] Un búfer que se va a rellenar con datos. No puede ser `NULL`.

## <a name="return-value"></a>Valor devuelto
 Si es correcto, devuelve `S_OK`; en caso contrario, devuelve un código de error.

## <a name="see-also"></a>Vea también
- [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)