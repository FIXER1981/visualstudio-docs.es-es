---
title: BPREQI_FIELDS | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- BPREQI_FIELDS
helpviewer_keywords:
- BPREQI_FIELDS enumeration
ms.assetid: 679e771e-4a79-484e-af37-f962ef4aa245
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a8ad9e4b6d83ebc05c78a8b84c0c06e00d7563bc
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68153225"
---
# <a name="bpreqi_fields"></a>BPREQI_FIELDS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Especifica la información que se va a recuperar sobre una solicitud de punto de interrupción.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
enum enum_BPREQI_FIELDS {   
   BPREQI_BPLOCATION   = 0x0001,  
   BPREQI_LANGUAGE     = 0x0002,  
   BPREQI_PROGRAM      = 0x0004,  
   BPREQI_PROGRAMNAME  = 0x0008,  
   BPREQI_THREAD       = 0x0010,  
   BPREQI_THREADNAME   = 0x0020,  
   BPREQI_PASSCOUNT    = 0x0040,  
   BPREQI_CONDITION    = 0x0080,  
   BPREQI_FLAGS        = 0x0100,  
   BPREQI_ALLOLDFIELDS = 0x01ff  
   BPREQI_VENDOR       = 0x0200,   // BP_REQUEST_INFO2 only  
   BPREQI_CONSTRAINT   = 0x0400,   // BP_REQUEST_INFO2 only  
   BPREQI_TRACEPOINT   = 0x0800,   // BP_REQUEST_INFO2 only  
   BPREQI_ALLFIELDS    = 0x0fff    // BP_REQUEST_INFO2 only  
};  
typedef DWORD BPREQI_FIELDS;  
```  
  
```csharp  
public enum enum_BPREQI_FIELDS {   
   BPREQI_BPLOCATION   = 0x0001,  
   BPREQI_LANGUAGE     = 0x0002,  
   BPREQI_PROGRAM      = 0x0004,  
   BPREQI_PROGRAMNAME  = 0x0008,  
   BPREQI_THREAD       = 0x0010,  
   BPREQI_THREADNAME   = 0x0020,  
   BPREQI_PASSCOUNT    = 0x0040,  
   BPREQI_CONDITION    = 0x0080,  
   BPREQI_FLAGS        = 0x0100,  
   BPREQI_ALLOLDFIELDS = 0x01ff  
   BPREQI_VENDOR       = 0x0200,   // BP_REQUEST_INFO2 only  
   BPREQI_CONSTRAINT   = 0x0400,   // BP_REQUEST_INFO2 only  
   BPREQI_TRACEPOINT   = 0x0800,   // BP_REQUEST_INFO2 only  
   BPREQI_ALLFIELDS    = 0x0fff    // BP_REQUEST_INFO2 only  
};  
```  
  
## <a name="members"></a>Miembros  
 BPREQI_BPLOCATION  
 Inicialice/use el `bpLocation` campo (ubicación del punto de interrupción) de la estructura [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) o [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) .  
  
 BPREQI_LANGUAGE  
 Inicialice o use el `guidLanguage` campo de la `BP_REQUEST_INFO` `BP_REQUEST_INFO2` estructura o.  
  
 BPREQI_PROGRAM  
 Inicialice o use el `pProgram` campo de la `BP_REQUEST_INFO` `BP_REQUEST_INFO2` estructura o.  
  
 BPREQI_PROGRAMNAME  
 Inicialice o use el `bstrProgramName` campo de la `BP_REQUEST_INFO` `BP_REQUEST_INFO2` estructura o.  
  
 BPREQI_THREAD  
 Inicialice o use el `pThread` campo de la `BP_REQUEST_INFO` `BP_REQUEST_INFO2` estructura o.  
  
 BPREQI_THREADNAME  
 Inicialice o use el `bstrThreadName` campo de la `BP_REQUEST_INFO` `BP_REQUEST_INFO2` estructura o.  
  
 BPREQI_PASSCOUNT  
 Inicialice o use el `bpPassCount` campo de la `BP_REQUEST_INFO` `BP_REQUEST_INFO2` estructura o.  
  
 BPREQI_CONDITION  
 Inicialice/use el `bpCondition` campo (condición de punto de interrupción) de la `BP_REQUEST_INFO` `BP_REQUEST_INFO2` estructura o.  
  
 BPREQI_FLAGS  
 Inicialice o use el `dwFlags` campo de la `BP_REQUEST_INFO` `BP_REQUEST_INFO2` estructura o.  
  
 BPREQI_ALLOLDFIELDS  
 Inicializar o utilizar todos los campos para el de la `BP_REQUEST_INFO` estructura.  
  
 BPREQI_VENDOR  
 Inicializar/usar el `guidVendor` campo de la `BP_REQUEST_INFO2` estructura.  
  
 BPREQI_CONSTRAINT  
 Inicializar/usar el `bstrConstraint` campo de la `BP_REQUEST_INFO2` estructura.  
  
 BPREQI_TRACEPOINT  
 Inicializar/usar el `bstrTracepoint` campo de la `BP_REQUEST_INFO2` estructura.  
  
 BPREQI_ALLFIELDS  
 Especifica todos los campos de la `BP_REQUEST_INFO2` estructura.  
  
## <a name="remarks"></a>Comentarios  
 Se pasa como argumento a los métodos [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md) y [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) para especificar los campos de las estructuras [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) y [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) que se van a inicializar.  
  
 Estas marcas también se usan para indicar los campos de las `BP_REQUEST_INFO` estructuras y que `BP_REQUEST_INFO2` se usan y son válidos cuando se devuelve cada estructura.  
  
 Estos valores se pueden combinar con una operación bit a bit `OR` .  
  
## <a name="requirements"></a>Requisitos  
 Encabezado: msdbg. h  
  
 Espacio de nombres: Microsoft. VisualStudio. Debugger. Interop  
  
 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Consulte también  
 [Enumeraciones](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)
