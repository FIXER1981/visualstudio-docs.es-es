---
title: CvWriteAlert (función) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cvmarkers/CvWriteAlertVA
- cvmarkers/CvWriteAlertVW
- cvmarkers/CvWriteAlertA
- cvmarkers/CvWriteAlertW
helpviewer_keywords:
- CvWriteAlertVW method
- CvWriteAlertA method
- CvWriteAlertVA method
- CvWriteAlertW method
ms.assetid: 937aa9d6-278a-4df3-bef7-151441df16d5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 56af9515fb9c066e56dd45a0fb91a95530f09799
ms.sourcegitcommit: 57d96de120e0574e506dfd80bb7adfbac73f96be
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85332173"
---
# <a name="cvwritealert-function"></a>Función CvWriteAlert
Escribe una alerta en el archivo de seguimiento del visualizador de simultaneidad.

## <a name="syntax"></a>Sintaxis

```C
HRESULT CvWriteAlertW(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ PCWSTR pMessage,
    ...
    );

HRESULT CvWriteAlertA(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ PCSTR pMessage,
    ...
    );

HRESULT CvWriteAlertVW(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ PCWSTR pMessage,
    _In_ va_list argList);

HRESULT CvWriteAlertVA(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ PCSTR pMessage,
    _In_ va_list argList);
```

#### <a name="parameters"></a>Parámetros
 `argList` Lista de argumentos.

 `pMarkerSeries` Contexto de la serie de marcador válido. No puede ser nulo.

 `pMessage` Cadena de formato de mensaje. No puede ser nulo.

## <a name="return-value"></a>Valor devuelto
 S_OK cuando el mensaje se ha escrito correctamente. Código de error en caso de que se hayan producido errores. Utilice macros SUCCEEDED/FAILED para comprobar si existe una condición de error.

## <a name="requirements"></a>Requisitos
 **Encabezado:** *cvmarkers.h*

 **Unicode:** CvWriteAlertW, CvWriteAlertVW

 **ANSI:** CvWriteAlertA, CvWriteAlertVA

## <a name="see-also"></a>Vea también
- [Referencia de la biblioteca C++](../profiling/cpp-library-reference.md)