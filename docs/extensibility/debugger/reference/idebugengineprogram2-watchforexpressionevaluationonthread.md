---
title: IDebugEngineProgram2::WatchForExpressionEvaluationOnThread | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
helpviewer_keywords:
- IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
ms.assetid: 01d05e77-8cac-4d1b-b19f-25756767ed27
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4c0572bfa8ebe1b70548483b17c58d08c8a0f9ca
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686956"
---
# <a name="idebugengineprogram2watchforexpressionevaluationonthread"></a>IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
Permite la evaluación de expresiones que se produzca en el subproceso determinado, incluso si se ha detenido el programa (o impide).

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT WatchForExpressionEvaluationOnThread( 
   IDebugProgram2*       pOriginatingProgram,
   DWORD                 dwTid,
   DWORD                 dwEvalFlags,
   IDebugEventCallback2* pExprCallback,
   BOOL                  fWatch
);
```

```csharp
int WatchForExpressionEvaluationOnThread( 
   IDebugProgram2       pOriginatingProgram,
   uint                  dwTid,
   uint                  dwEvalFlags,
   IDebugEventCallback2 pExprCallback,
   int                   fWatch
);
```

#### <a name="parameters"></a>Parámetros
 `pOriginatingProgram`

 [in] Un [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objeto que representa el programa que está evaluando una expresión.

 `dwTid`

 [in] Especifica el identificador del subproceso.

 `dwEvalFlags`

 [in] Una combinación de marcas de la [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) enumeración que especifican cómo se puede realizar la evaluación.

 `pExprCallback`

 [in] Un [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) objeto que se usará para enviar eventos de depuración que se producen durante la evaluación de expresión.

 `fWatch`

 [in] Si es distinto de cero (`TRUE`), permite la evaluación de expresiones en el subproceso identificado por `dwTid`; en caso contrario, cero (`FALSE`) no permite la evaluación de expresiones en ese subproceso.

## <a name="return-value"></a>Valor devuelto
 Si es correcto, devuelve `S_OK`; en caso contrario, devuelve un código de error.

## <a name="remarks"></a>Comentarios
 Cuando el Administrador de depuración de la sesión (SDM) solicita un programa, identificado por el `pOriginatingProgram` parámetro, para evaluar una expresión, notifica a todos los demás programas asociados mediante una llamada a este método.

 Evaluación de expresiones en un programa puede hacer que el código se ejecute en otro, debido a la evaluación de la función o de evaluación de cualquier `IDispatch` propiedades. Por este motivo, este método permite la evaluación de expresiones ejecutar y completar, aunque se puede detener el subproceso en este programa.

## <a name="see-also"></a>Vea también
- [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)
- [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)