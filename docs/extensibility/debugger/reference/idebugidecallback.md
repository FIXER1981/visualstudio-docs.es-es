---
title: IDebugIDECallback | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugIDECallback interface
ms.assetid: 8d31adc0-1c44-4658-8d4f-f4b73e35f4a6
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 585ff354cef9686097325ea4dea25cd08c4cbb1b
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80727827"
---
# <a name="idebugidecallback"></a>IDebugIDECallback
> [!IMPORTANT]
> En Visual Studio 2015, esta manera de implementar evaluadores de expresiones está en desuso. Para obtener información sobre la implementación de evaluadores de expresiones CLR, consulte [evaluadores](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) de expresiones CLR y [ejemplo de evaluador de expresiones administradas](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Permite a un evaluador de expresiones (EE) mostrar un mensaje en la ventana de salida del depurador.

## <a name="syntax"></a>Sintaxis

```
IDebugIDECallback : IUnknown
```

## <a name="notes-for-implementers"></a>Notas para los implementadores
 Esta devolución de llamada se implementa mediante el motor de depuración administrado.

## <a name="notes-for-callers"></a>Notas para llamadores
 Puede ser utilizado por un evaluador de expresiones para enviar la salida a la ventana de salida del depurador.

## <a name="methods"></a>Métodos
 Esta interfaz implementa el método siguiente:

|Método|Descripción|
|------------|-----------------|
|[DisplayMessage](../../../extensibility/debugger/reference/idebugidecallback-displaymessage.md)|Envía la cadena de mensaje especificada a la ventana de salida del depurador.|

## <a name="requirements"></a>Requisitos
 Encabezado: EE. h

 Espacio de nombres: Microsoft. VisualStudio. Debugger. Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll
