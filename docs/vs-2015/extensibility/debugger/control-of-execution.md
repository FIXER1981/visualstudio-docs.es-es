---
title: Control de la ejecución | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], control of execution
ms.assetid: 97071846-007e-450f-95a6-f072d0f5e61e
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c885c0c983e6fafd69d55b3d68f8ed6e8ff2628c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "86387270"
---
# <a name="control-of-execution"></a>Control de ejecución
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

El motor DE depuración (DE) envía normalmente uno de los siguientes eventos como el último evento de Inicio:  
  
- El evento de punto de entrada, si se asocia a un programa recién iniciado  
  
- Evento de carga completada, si se va a asociar a un programa que ya se está ejecutando  
  
  Ambos eventos están deteniendo eventos, lo que significa que el DE espera una respuesta del usuario por medio del IDE. Para obtener más información, vea [modos operativos](../../extensibility/debugger/operational-modes.md).  
  
## <a name="stopping-event"></a>Detener evento  
 Cuando se envía un evento de detención a la sesión de depuración:  
  
1. El programa y el subproceso que contienen el puntero de instrucción actual se pueden obtener de la interfaz de eventos.  
  
2. El IDE determina el archivo de código fuente actual y la posición, que aparece resaltada en el editor.  
  
3. La sesión de depuración normalmente responde a este primer evento de detención llamando al método **continue** del programa.  
  
4. Después, el programa se ejecuta hasta que encuentra una condición de detención, como al golpear un punto de interrupción, en cuyo caso el DE envía un evento DE punto de interrupción a la sesión de depuración. El evento DE punto de interrupción es un evento de detención y el DE vuelve a esperar una respuesta del usuario.  
  
5. Si el usuario elige depurar paso a paso por instrucciones, sobre o fuera de una función, el IDE solicitará a la sesión de depuración que llame al método del programa `Step` , pasándole la unidad de paso (instrucción, instrucción o línea) y el tipo de paso, es decir, si se depurará paso a paso por instrucciones, por encima o fuera de la función. Una vez completado el paso, el DE envía un evento Step complete a la sesión de depuración, que es un evento DE detención.  
  
    o bien  
  
    Si el usuario decide continuar la ejecución desde el puntero de instrucción actual, el IDE solicitará a la sesión de depuración que llame al método **Execute** del programa. El programa reanuda la ejecución hasta que encuentra la siguiente condición de detención.  
  
    o bien  
  
    Si la sesión de depuración es omitir un evento de detención determinado, la sesión de depuración llama al método **continue** del programa. Si el programa se detuvo paso a paso, sobre o fuera de una función cuando se produjo la condición de detención, continúa con el paso.  
  
   Mediante programación, cuando el DE encuentra una condición DE detención, envía eventos de detención como [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) o [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) al administrador de depuración de sesión (SDM) mediante una interfaz [IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md) . El objeto DE pasa las interfaces [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) y [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) que representan el programa y el subproceso que contiene el puntero de instrucción actual. El SDM llama a [IDebugThread2:: EnumFrameInfo](../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) para obtener el marco de pila superior y llama a [IDebugStackFrame2:: GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) para obtener el contexto de documento asociado al puntero de instrucción actual. Este contexto de documento suele ser un nombre de archivo de código fuente, una línea y un número de columna. El IDE los usa para resaltar el código fuente que contiene el puntero de instrucción actual.  
  
   El SDM normalmente responde a este primer evento de detención llamando a [IDebugProgram2:: Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md). Después, el programa se ejecuta hasta que encuentra una condición de detención, como alcanzar un punto de interrupción, en cuyo caso el DE envía una [interfaz IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) al SDM. El evento DE punto de interrupción es un evento de detención y el DE vuelve a esperar una respuesta del usuario.  
  
   Si el usuario elige depurar paso a paso por instrucciones, sobre o fuera de una función, el IDE solicita al SDM que llame a [IDebugProgram2:: Step](../../extensibility/debugger/reference/idebugprogram2-step.md), pasándole el [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) (instrucción, instrucción o línea) y [STEPKIND](../../extensibility/debugger/reference/stepkind.md), es decir, si se va a depurar paso a paso por, sobre o fuera de la función. Una vez completado el paso, el DE envía una interfaz [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) al SDM, que es un evento de detención.  
  
   Si el usuario decide continuar la ejecución desde el puntero de instrucción actual, el IDE pide al SDM que llame a [IDebugProgram2:: Execute](../../extensibility/debugger/reference/idebugprogram2-execute.md). El programa reanuda la ejecución hasta que encuentra la siguiente condición de detención.  
  
   Si el paquete de depuración va a omitir un evento de detención determinado, el paquete de depuración llama al SDM, que llama a [IDebugProgram2:: Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md). Si el programa se detuvo paso a paso, sobre o fuera de una función cuando se produjo la condición de detención, continúa con el paso. Esto implica que el programa mantiene un estado de ejecución paso a paso para que sepa cómo continuar.  
  
   Las llamadas que el SDM realiza a `Step` , **ejecutan**y **continúan** son asincrónicas, lo que significa que el SDM espera que la llamada se devuelva rápidamente. Si el DE envía a un evento de detención de SDM en el mismo subproceso antes `Step` de, **Execute**o **continue** devuelve, el SDM deja de responder.  
  
## <a name="see-also"></a>Consulte también  
 [Tareas de depuración](../../extensibility/debugger/debugging-tasks.md)
