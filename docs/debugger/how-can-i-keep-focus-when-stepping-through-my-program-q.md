---
title: Mantener el foco mientras se recorre mi aplicación | Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.stepping
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], stepping
- focus, keeping
- stepping, focus
- windows, troubleshooting activation
ms.assetid: 11a30580-3a1a-4be8-a241-0abdc758302e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a409ee1e8d1b633689a0c33e39e300071b9b4d83
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56690076"
---
# <a name="how-can-i-keep-focus-when-stepping-through-my-app"></a>¿Cómo puedo mantener el foco mientras se recorre mi aplicación?
## <a name="description"></a>Descripción
 El programa presenta un problema de activación de ventana. Si se ejecuta el programa paso a paso con el depurador, se interfiere con la capacidad de reproducir el problema debido a que el programa pierde el foco. ¿Existe algún modo de evitar esto?

## <a name="solution"></a>Soluciones
 Si dispone de un segundo equipo, utilice la función de depuración remota. Puede ejecutar el programa en el equipo remoto mientras ejecuta el depurador en el equipo host. Para obtener más información, consulte [Cómo: seleccionar un equipo remoto](/previous-versions/visualstudio/visual-studio-2010/w8wtw2f3(v=vs.100)).

## <a name="see-also"></a>Vea también
- [Preguntas más frecuentes sobre la depuración de código nativo](../debugger/debugging-native-code-faqs.md)
- [Asociar a procesos en ejecución](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)
- [Depuración de código nativo](../debugger/debugging-native-code.md)