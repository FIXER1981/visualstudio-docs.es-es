---
title: BP_FLAGS90 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- BP_FLAGS90 enumeration
ms.assetid: 3e5a06c5-fb30-4b8a-b2d5-4a0570fc80bd
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9f7192eb7b2fa6d8bc886c0e601788ecba8eebcd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "68153499"
---
# <a name="bpflags90"></a>BP_FLAGS90
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Enumera los valores válidos para las marcas opcionales. Las marcas opcionales pueden utilizarse para especificar información adicional al establecer un punto de interrupción. Esta enumeración se extiende el [BP_FLAGS](../../../extensibility/debugger/reference/bp-flags.md) enumeración.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
enum enum_BP_FLAGS90  
{  
   // VS 8.0 values  
   BP90_FLAG_NONE               = 0x0000,  
   BP90_FLAG_MAP_DOCPOSITION    = 0x0001,  
   BP90_FLAG_DONT_STOP          = 0x0002,  
  
   // Values added in VS 9.0  
   BP90_FLAG_TRACEPOINT_CONTINUE = 0x0004,  
};  
typedef DWORD BP_FLAGS90;  
```  
  
```csharp  
public enum enum_BP_FLAGS90  
{  
   // VS 8.0 values  
   BP90_FLAG_NONE                = 0x0000,  
   BP90_FLAG_MAP_DOCPOSITION     = 0x0001,  
   BP90_FLAG_DONT_STOP           = 0x0002,  
  
   // Values added in VS 9.0  
   BP90_FLAG_TRACEPOINT_CONTINUE = 0x0004,  
};  
```  
  
#### <a name="parameters"></a>Parámetros  
 BP90_FLAG_NONE  
 No especifica ninguna marca de punto de interrupción.  
  
 BP90_FLAG_MAP_DOCPOSITION  
 Especifica que el motor de depuración (DE) debe asignar el punto de interrupción mediante el uso de la posición del documento. Esto solo es aplicable a puntos de interrupción establecidos en archivos de origen orientado a secuencias de comandos, como las páginas Active Server (ASP).  
  
 BP90_FLAG_DONT_STOP  
 Especifica que el punto de interrupción debe procesarse por el motor de depuración, pero que el motor de depuración en última instancia, no debería detener es decir, un [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md) no se debe enviar el objeto de evento. Esta marca está diseñada para su uso principalmente con puntos de seguimiento.  
  
 BP90_FLAG_TRACEPOINT_CONTINUE  
 Usa el motor de depuración nativo para determinar si se debe borrar el estado de ejecución paso a paso. Difiere BP90_FLAG_DONT_STOP porque BP90_FLAG_DONT_STOP no se establece si el punto de seguimiento ejecuta una macro.  
  
## <a name="requirements"></a>Requisitos  
 Encabezado: Msdbg90.h  
  
 Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop  
  
 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
