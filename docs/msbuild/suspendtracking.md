---
title: SuspendTracking | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- SuspendTracking
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- SuspendTracking
ms.assetid: f5e06e5a-8083-444c-99c1-07ba834226b5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cc2a8b3dc2f5940c64be870df452b088dce7bc0e
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56632464"
---
# <a name="suspendtracking"></a>SuspendTracking
Suspende el seguimiento en el contexto actual.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT WINAPI SuspendTracking(void);
```

## <a name="return-value"></a>Valor devuelto
 Un elemento **HRESULT** con el conjunto de bits **SUCCEEDED** si el seguimiento se ha suspendido.

## <a name="requirements"></a>Requisitos
 **Encabezado**: *FileTracker.h*

## <a name="see-also"></a>Vea también
- [ResumeTracking](../msbuild/resumetracking.md)