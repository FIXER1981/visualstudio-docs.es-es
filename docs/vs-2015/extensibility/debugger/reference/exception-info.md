---
title: EXCEPTION_INFO | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- EXCEPTION_INFO
helpviewer_keywords:
- EXCEPTION_INFO structure
ms.assetid: d046957a-b97d-420b-b46b-c67cbaef709e
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 66af4d95707be99865df3df32751215cf5eb10b2
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68181174"
---
# <a name="exception_info"></a>EXCEPTION_INFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Describe una excepción o un error en tiempo de ejecución producido por el programa que se está depurando.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
typedef struct tagEXCEPTION_INFO {   
   IDebugProgram2* pProgram;  
   BSTR            bstrProgramName;  
   BSTR            bstrExceptionName;  
   DWORD           dwCode;  
   EXCEPTION_STATE dwState;  
   GUID            guidType;  
} EXCEPTION_INFO;  
```  
  
```csharp  
public struct EXCEPTION_INFO {   
   public IDebugProgram2 pProgram;  
   public string         bstrProgramName;  
   public string         bstrExceptionName;  
   public uint           dwCode;  
   public uint           dwState;  
   public Guid           guidType;  
};  
```  
  
## <a name="members"></a>Miembros  
 pProgram  
 Objeto [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) que representa el programa en el que se produjo la excepción.  
  
 bstrProgramName  
 Nombre del programa en el que se produjo la excepción.  
  
 bstrExceptionName  
 Nombre de la excepción.  
  
 dwCode  
 Código de identificación para la excepción o el error en tiempo de ejecución.  
  
 dwState  
 Un valor de la enumeración [EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md) que define el estado de la excepción.  
  
 guidType  
 Identificador de idioma GUID, ya sea `guidLang` o `guidEng` .  
  
## <a name="remarks"></a>Comentarios  
 Esta estructura se pasa como parámetro a los métodos [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md) y [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md) . Esta estructura también se pasa al método [GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md) que se va a rellenar.  
  
## <a name="requirements"></a>Requisitos  
 Encabezado: msdbg. h  
  
 Espacio de nombres: Microsoft. VisualStudio. Debugger. Interop  
  
 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Consulte también  
 [Estructuras y uniones](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)   
 [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)   
 [GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md)
