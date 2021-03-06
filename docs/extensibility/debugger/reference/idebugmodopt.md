---
title: IDebugModOpt | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugModOpt interface
ms.assetid: ebd525e3-d140-4071-9d8c-41871de4125e
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e142ed1229f59cfc22ff33cba48e9e35eb4e4406
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80726977"
---
# <a name="idebugmodopt"></a>IDebugModOpt
Representa un modificador opcional Debug.

## <a name="syntax"></a>Sintaxis

```
IDebugModOpt : IUnknown
```

## <a name="notes-for-callers"></a>Notas para llamadores
 Se obtiene a partir de un objeto [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) que representa una clase o un método.

## <a name="methods"></a>Métodos
 Esta interfaz implementa el método siguiente:

|Método|Descripción|
|------------|-----------------|
|[GetModOpts](../../../extensibility/debugger/reference/idebugmodopt-getmodopts.md)|Recupera una lista de modificadores opcionales.|

## <a name="requirements"></a>Requisitos
 Encabezado: SH. h

 Espacio de nombres: Microsoft. VisualStudio. Debugger. Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll
