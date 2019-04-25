---
title: SetThreadCount | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
apiname:
- SetThreadCount
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- SetThreadCount
ms.assetid: 335335a5-8ca0-4e18-95f5-62aa6a691386
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 656e491e683c7ec2de23ea7e49938e833af3a295
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56709621"
---
# <a name="setthreadcount"></a>SetThreadCount
Establece el recuento de subprocesos globales y asigna ese recuento al subproceso actual.

## <a name="syntax"></a>Sintaxis

```cmd
HRESULT WINAPI SetThreadCount(int threadCount);
```

#### <a name="parameters"></a>Parámetros
[in] `threadCount`

 El número de subprocesos que se va a usar.

## <a name="return-value"></a>Valor devuelto
 Un elemento **HRESULT** con el conjunto de bits **SUCCEEDED** si el recuento de subprocesos se ha actualizado.

## <a name="requirements"></a>Requisitos
 **Encabezado**: *FileTracker.h*