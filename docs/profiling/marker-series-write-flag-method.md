---
title: marker_series::write_flag (Método) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cvmarkersojb/Concurrency, diagnostic::marker_series::write_flag
helpviewer_keywords:
- Concurrency, diagnostic::marker_series::write_flag method
ms.assetid: ca07f388-e5d5-46fd-b991-fe6e9029a68f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: edd141f6b99dc3836d99ebdbc4aab9af7150e4ff
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "85329229"
---
# <a name="marker_serieswrite_flag-method"></a>Método marker_series::write_flag
Escribe una marca en el archivo de seguimiento del visualizador de simultaneidad.

## <a name="syntax"></a>Sintaxis

```cpp
void write_flag(
   _In_ LPCTSTR _Format,
   ...
);
void write_flag(
   marker_importance _Importance,
   _In_ LPCTSTR _Format,
   ...
);
void write_flag(
   int _Category,
   _In_ LPCTSTR _Format,
   ...
);
void write_flag(
   marker_importance _Importance,
   int _Category,
   _In_ LPCTSTR _Format,
   ...
);
```

#### <a name="parameters"></a>Parámetros
 `_Format` Una cadena de formato compuesto que contiene texto combinado con cero o más elementos de formato, que corresponden a objetos de la lista de argumentos.

 `_Importance` Nivel de importancia.

 `_Category` Categoría.

## <a name="requirements"></a>Requisitos
 **Encabezado:** *cvmarkersobj.h*

 **Espacio de nombres**: Concurrency::diagnostic

## <a name="see-also"></a>Vea también
- [Clase marker_series](../profiling/marker-series-class.md)