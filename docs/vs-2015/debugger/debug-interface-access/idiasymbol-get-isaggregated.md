---
title: IDiaSymbol::get_isAggregated | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isAggregated method
ms.assetid: 24d280ef-6ea3-4958-9418-4ad3ca7c67c1
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 406c57c6b1127e7a36f5653299e04eef5f5f9e2c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "58996316"
---
# <a name="idiasymbolgetisaggregated"></a>IDiaSymbol::get_isAggregated
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Recupera una marca que especifica si el símbolo de datos forma parte de un agregado o una colección de símbolos; el compilador tratará símbolos agregados como entidades independientes, pero realmente son parte de un único símbolo de mayor tamaño.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
HRESULT get_isAggregated(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pFlag`  
 [out] Devuelve `TRUE` si los datos forman parte de una agregación de símbolos divididos desde un símbolo de elemento primario; de lo contrario, devuelve `FALSE`.  
  
## <a name="return-value"></a>Valor devuelto  
 Si es correcto, devuelve `S_OK`; en caso contrario, devuelve `S_FALSE` o un código de error.  
  
> [!NOTE]
>  Un valor devuelto de `S_FALSE` significa que la propiedad no está disponible para el símbolo.  
  
## <a name="remarks"></a>Comentarios  
 El [Get_issplitted](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md) método es `TRUE` para el símbolo que es el elemento primario de los símbolos agregados.  
  
## <a name="requirements"></a>Requisitos  
  
|Requisito|Descripción|  
|-----------------|-----------------|  
|Encabezado:|dia2.h|  
|Versión:|SDK de DIA v8.0|  
  
## <a name="see-also"></a>Vea también  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSymbol::get_isSplitted](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md)
