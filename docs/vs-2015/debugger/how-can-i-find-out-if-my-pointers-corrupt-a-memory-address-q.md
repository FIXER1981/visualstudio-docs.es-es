---
title: Cómo averiguar si los punteros dañan una dirección de memoria | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- addresses, pointers corrupting memory address
- memory, corruption
- pointers, corrupting memory addresses
- memory address corruption by pointers
- debugging [C++], memory corruption
- corrupted memory address
ms.assetid: a147c939-4fb1-415c-8410-cf303781e9e8
caps.latest.revision: 22
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1d4f23b885b2e72e53d288946df18e038d9d956d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "77476777"
---
# <a name="how-can-i-find-out-if-my-pointers-corrupt-a-memory-address"></a>Cómo averiguar si los punteros dañan una dirección de memoria
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Descripción del problema  
 Parece que uno de los punteros está dañando la memoria en la dirección 0x00408000. ¿Cómo se puede averiguar lo que está ocurriendo allí?  
  
## <a name="solution"></a>Soluciones  
  
#### <a name="check-for-heap-corruption"></a>Compruebe si el montón está dañado  
  
- La mayoría de los daños en la memoria se deben en realidad a que el montón está dañado. Pruebe a usar la utilidad de marcas global (gflags.exe) o pageheap.exe. Consulte [GFlags y PageHeap](/windows-hardware/drivers/debugger/gflags-and-pageheap) y [Cómo usar la utilidad PageHeap para detectar errores de memoria en un proyecto Microsoft Visual C++](https://support.microsoft.com/help/264471/how-to-use-the-pageheap-utility-to-detect-memory-errors-in-a-microsoft).
  
#### <a name="to-find-where-the-memory-address-is-modified"></a>Para averiguar dónde se ha modificado la dirección de la memoria  
  
1. Establezca un punto de interrupción de datos en 0x00408000. Vea [Establecer un punto de interrupción de cambio de datos (solo C++ nativo)](../debugger/using-breakpoints.md#BKMK_set_a_data_breakpoint_native_cplusplus_only).  
  
2. Cuando alcance el punto de interrupción, utilice la ventana **Memoria** para ver el contenido de la memoria a partir de la dirección 0x00408000. Para obtener más información, vea [Ventanas de memoria](../debugger/memory-windows.md).  
  
## <a name="see-also"></a>Consulte también  
 [Preguntas más frecuentes sobre depuración de código nativo](../debugger/debugging-native-code-faqs.md)   
 [Depuración de código nativo](../debugger/debugging-native-code.md)
