---
title: Dimensión | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Dimension Symbol
ms.assetid: 94f791da-bfea-454f-8a14-da31e8e1596a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 97b03f1a3ceb8424cc3e533512f6d0d3e034f791
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56637404"
---
# <a name="dimension"></a>Dimensión
Cada matriz de FORTRAN tiene una dimensión que se identifica mediante un `SymTagDimension` símbolos.

## <a name="properties"></a>Propiedades
 La siguiente tabla muestra propiedades adicionales de válido para este tipo de símbolo.

|Propiedad.|Tipo de datos|Descripción|
|--------------|---------------|-----------------|
|[IDiaSymbol::get_lowerBound](../../debugger/debug-interface-access/idiasymbol-get-lowerbound.md)|`IDiaSymbol*`|Límite inferior de una dimensión de matriz de FORTRAN.|
|[IDiaSymbol::get_lowerBoundId](../../debugger/debug-interface-access/idiasymbol-get-lowerboundid.md)|`DWORD`|Id. del símbolo de límite inferior.|
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|Id. de índice de símbolo.|
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Devuelve `SymTagDimension` (uno de los [SymTagEnum (enumeración)](../../debugger/debug-interface-access/symtagenum.md) valores).|
|[IDiaSymbol::get_upperBound](../../debugger/debug-interface-access/idiasymbol-get-upperbound.md)|`IDiaSymbol*`|Límite superior de una dimensión de matriz de FORTRAN.|
|[IDiaSymbol::get_upperBoundId](../../debugger/debug-interface-access/idiasymbol-get-upperboundid.md)|`DWORD`|Id. del símbolo de límite superior.|

## <a name="see-also"></a>Vea también
- [ArrayType](../../debugger/debug-interface-access/arraytype.md)
- [Jerarquía de clases de tipos de símbolos](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)