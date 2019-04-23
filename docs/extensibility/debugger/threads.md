---
title: Subprocesos | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], threads
- threading [Debugging SDK]
ms.assetid: 2243d24a-c3d2-41d1-abbb-6db21a2db9ee
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5d931568258099fa4a8fe8f3b82d3fe50d5a3e35
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "60099778"
---
# <a name="threads"></a>Subprocesos
En la arquitectura de depurador, un *subproceso*:

- Es la unidad fundamental del cálculo. Un subproceso ejecuta secuencialmente las instrucciones dentro del contexto de una misma pila de llamadas, mover desde el contexto de un código a la siguiente.

- Puede identificar el propio y el programa que se está ejecutando. Pueden denominados, suspender y reanudar subprocesos. Un subproceso también puede enumerar sus marcos de pila asociado y, en determinadas condiciones, se puede mover a otro marco de pila. Dado el contexto de un marco de pila, un subproceso puede devolver su subproceso lógico asociado, si existe. Un subproceso tiene propiedades, como un recuento de suspensión, que se pueden mostrar en el **subprocesos** ventana del IDE.

- Se representa mediante un [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) interfaz, suelen ser creado por un motor de depuración (DE) o una máquina virtual como consecuencia de ejecutar un programa.

## <a name="see-also"></a>Vea también
- [Programas](../../extensibility/debugger/programs.md)
- [Marcos de pila](../../extensibility/debugger/stack-frames.md)
- [Motor de depuración](../../extensibility/debugger/debug-engine.md)
- [Conceptos del depurador](../../extensibility/debugger/debugger-concepts.md)
- [Administrador de depuración de sesión](../../extensibility/debugger/session-debug-manager.md)