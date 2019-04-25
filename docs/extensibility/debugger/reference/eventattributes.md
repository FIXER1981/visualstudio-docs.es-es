---
title: EVENTATTRIBUTES | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- EVENTATTRIBUTES
helpviewer_keywords:
- EVENTATTRIBUTES enumeration
ms.assetid: 04db10f7-df31-4464-98e8-b3777428179e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 58417471e37dd335c2fa751492f2db357274417a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686904"
---
# <a name="eventattributes"></a>EVENTATTRIBUTES
Especifica los atributos del evento.

## <a name="syntax"></a>Sintaxis

```cpp
enum enum_EVENTATTRIBUTES {
    EVENT_ASYNCHRONOUS          = 0x0000,
    EVENT_SYNCHRONOUS           = 0x0001,
    EVENT_STOPPING              = 0x0002,
    EVENT_ASYNC_STOP            = 0x0002,
    EVENT_SYNC_STOP             = 0x0003,
    EVENT_IMMEDIATE             = 0x0004,
    EVENT_EXPRESSION_EVALUATION = 0x0008
};
typedef DWORD EVENTATTRIBUTES;
```

```csharp
public enum enum_EVENTATTRIBUTES {
    EVENT_ASYNCHRONOUS          = 0x0000,
    EVENT_SYNCHRONOUS           = 0x0001,
    EVENT_STOPPING              = 0x0002,
    EVENT_ASYNC_STOP            = 0x0002,
    EVENT_SYNC_STOP             = 0x0003,
    EVENT_IMMEDIATE             = 0x0004,
    EVENT_EXPRESSION_EVALUATION = 0x0008
};
```

## <a name="members"></a>Miembros
EVENT_ASYNCHRONOUS indica que el evento es asincrónico y no se necesita ninguna respuesta al evento.

EVENT_SYNCHRONOUS indica que el evento es sincrónico; responder por medio de [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md).

EVENT_STOPPING indica que se trata de un evento de detención. Se debe combinar con `EVENT_ASYNCHRONOUS` o `EVENT_SYNCHRONOUS`.

EVENT_ASYNC_STOP indica un evento de detención asincrónica. Actualmente no hay ningún evento de este tipo. Esta marca es solo un marcador de posición.

EVENT_SYNC_STOP indica un evento de detención sincrónica (una combinación de `EVENT_SYNCHRONOUS` y `EVENT_STOPPING`). Este valor se usa un motor de depuración (DE) cuando envía un evento de detención. La respuesta se realiza mediante una llamada a [Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md), [paso](../../../extensibility/debugger/reference/idebugprogram2-step.md), o [continuar](../../../extensibility/debugger/reference/idebugprogram2-continue.md).

EVENT_IMMEDIATE indica un evento que se envía de forma inmediata y sincrónicamente al IDE. Esta marca se combina con otras marcas como `EVENT_ASYNCHRONOUS`, `EVENT_SYNCHRONOUS`, o `EVENT_SYNC_STOP` para indicar el tipo de evento y el hecho de que se conoce el mecanismo de respuesta (si existe).

El evento EVENT_EXPRESSION_EVALUATION es el resultado de evaluación de expresiones.

## <a name="remarks"></a>Comentarios
Estos valores se pasan en el `dwAttrib` parámetro de la [eventos](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) método.

Estos valores se pueden combinar con un bit a bit `OR`.

## <a name="requirements"></a>Requisitos
Encabezado: msdbg.h

Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [Enumeraciones](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)
- [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
