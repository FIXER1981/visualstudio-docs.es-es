---
title: CvReleaseProvider (función) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvReleaseProvider
helpviewer_keywords:
- CvReleaseProvider method
ms.assetid: 8d74379e-295d-452b-bd5f-0769df387d4f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0008b7476290558c098b2241fde5c9b209933a0a
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56606763"
---
# <a name="cvreleaseprovider-function"></a>Función CvReleaseProvider
Libera el proveedor de marcadores. Liberar el proveedor de marcadores no afectará a la serie de marcadores de este proveedor creada anteriormente. La serie de marcadores debe liberarse por separado mediante la llamada de CvReleaseMarkerSeries. Si no se puede liberar el proveedor, se produce una pérdida de memoria.

## <a name="syntax"></a>Sintaxis

```C
HRESULT CvReleaseProvider(
   _In_ PCV_PROVIDER pProvider
);
```

#### <a name="parameters"></a>Parámetros
 `pProvider` Contexto de proveedor. No puede ser nulo.

## <a name="return-value"></a>Valor devuelto
 S_OK cuando el proveedor se libera correctamente, o código de error en caso de que se hayan producido errores. Utilice macros SUCCEEDED/FAILED para comprobar si existe una condición de error.

## <a name="requirements"></a>Requisitos
 **Encabezado:** *cvmarkers.h*

## <a name="see-also"></a>Vea también
- [Referencia de la biblioteca C++](../profiling/cpp-library-reference.md)