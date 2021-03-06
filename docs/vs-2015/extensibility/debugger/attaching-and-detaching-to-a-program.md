---
title: Adjuntar y desasociar a un programa | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, attaching to programs
- debug engines, detaching from programs
ms.assetid: 79dcbb9b-c7f8-40fc-8a00-f37fe1934f51
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6e232a6f7fcb8813670ca6d949fdb6b3287bb79c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68146445"
---
# <a name="attaching-and-detaching-to-a-program"></a>Asociación a un programa y desasociación
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Para adjuntar el depurador es necesario enviar la secuencia correcta de métodos y eventos con los atributos adecuados.  
  
## <a name="sequence-of-methods-and-events"></a>Secuencia de métodos y eventos  
  
1. El administrador de depuración de sesión (SDM) llama al método [AutoAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) .  
  
    Según el modelo de proceso del motor DE depuración (DE), el `IDebugProgramNodeAttach2::OnAttach` método devuelve uno de los siguientes métodos, que determina lo que ocurre a continuación.  
  
    Si `S_FALSE` se devuelve, el motor de depuración se ha adjuntado correctamente al programa. De lo contrario, se llama al método [Attach](../../extensibility/debugger/reference/idebugengine2-attach.md) para completar el proceso de asociación.  
  
    Si `S_OK` se devuelve, el de se va a cargar en el mismo proceso que el SDM. El SDM realiza las siguientes tareas:  
  
   1. Llama a [GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md) para obtener la información del motor de de.  
  
   2. Crea el DE.  
  
   3. Llama a [Attach](../../extensibility/debugger/reference/idebugengine2-attach.md).  
  
2. El DE envía un [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) al SDM con un `EVENT_SYNC` atributo.  
  
3. El DE envía un [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) al SDM con un `EVENT_SYNC` atributo.  
  
4. El DE envía un [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) al SDM con un `EVENT_SYNC_STOP` atributo.  
  
   Desasociar de un programa es un proceso sencillo y de dos pasos, como se indica a continuación:  
  
5. El SDM llama a [detach](../../extensibility/debugger/reference/idebugprogram2-detach.md).  
  
6. El DE envía un [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md).  
  
## <a name="see-also"></a>Consulte también  
 [Llamada a eventos del depurador](../../extensibility/debugger/calling-debugger-events.md)
