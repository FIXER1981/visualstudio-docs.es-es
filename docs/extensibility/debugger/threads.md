---
title: Subprocesos | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], threads
- threading [Debugging SDK]
ms.assetid: 2243d24a-c3d2-41d1-abbb-6db21a2db9ee
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8ed5c06e0c42dac1f0539cc2c7c5886d95b23ae1
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80712481"
---
# <a name="threads"></a>Subprocesos
En la arquitectura del depurador, un *subproceso*:

- Es la unidad fundamental de cálculo. Un subproceso ejecuta secuencialmente sus instrucciones en el contexto de una sola pila de llamadas, pasando de un contexto de código al siguiente.

- Puede identificarse y el programa en el que se está ejecutando. Los subprocesos se pueden denominar, suspender y reanudar. Un subproceso también puede enumerar sus marcos de pila asociados y, en algunas condiciones, se puede desplace a otro marco de pila. Dado el contexto de un marco de pila, un subproceso puede devolver su subproceso lógico asociado, si existe. Un subproceso tiene propiedades, como un recuento de suspensión, que se pueden mostrar en la ventana **subprocesos** del IDE.

- Se representa mediante una interfaz [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) , creada normalmente por un motor de depuración (de) o una máquina virtual como consecuencia de la ejecución de un programa.

## <a name="see-also"></a>Vea también
- [Programs](../../extensibility/debugger/programs.md)
- [Marcos de pila](../../extensibility/debugger/stack-frames.md)
- [Motor de depuración](../../extensibility/debugger/debug-engine.md)
- [Conceptos del depurador](../../extensibility/debugger/debugger-concepts.md)
- [Administrador de depuración de sesión](../../extensibility/debugger/session-debug-manager.md)
