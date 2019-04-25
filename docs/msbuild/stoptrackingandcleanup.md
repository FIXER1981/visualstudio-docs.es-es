---
title: StopTrackingAndCleanup | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- StopTrackingAndCleanup
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- StopTrackingAndCleanup
ms.assetid: 9f8c5994-2dfc-43c3-a5fb-89b2f8990429
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 56f4fb82ab0e9792cadbeeea05499744e4c8ce46
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56621310"
---
# <a name="stoptrackingandcleanup"></a>StopTrackingAndCleanup
Detiene todo el seguimiento y libera la memoria que ha usado la sesión de seguimiento.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT WINAPI StopTrackingAndCleanup(void);
```

## <a name="return-value"></a>Valor devuelto
 Devuelve un elemento **HRESULT** con el conjunto de bits **SUCCEEDED** si el seguimiento se ha detenido.

## <a name="requirements"></a>Requisitos
 **Encabezado**: *FileTracker.h*

## <a name="see-also"></a>Vea también
- [StartTrackingContext](../msbuild/starttrackingcontext.md)