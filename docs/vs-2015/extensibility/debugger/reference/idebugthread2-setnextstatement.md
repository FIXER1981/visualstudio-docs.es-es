---
title: 'IDebugThread2:: SetNextStatement | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugThread2::SetNextStatement
helpviewer_keywords:
- IDebugThread2::SetNextStatement
ms.assetid: 9e2834dd-4ecf-45af-8e6c-f9318ebdac06
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 755044ec1d713075c1c1fd3165254ba192943288
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68152960"
---
# <a name="idebugthread2setnextstatement"></a>IDebugThread2::SetNextStatement
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Establece el puntero de instrucción actual en el contexto de código especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
HRESULT SetNextStatement (   
   IDebugStackFrame2*  pStackFrame,  
   IDebugCodeContext2* pCodeContext  
);  
```  
  
```csharp  
int SetNextStatement (   
   IDebugStackFrame2  pStackFrame,  
   IDebugCodeContext2 pCodeContext  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pStackFrame`  
 Reservado para uso futuro; establecer en un valor null.  
  
 `pCodeContext`  
 de Un objeto [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) que describe la ubicación del código que se va a ejecutar y su contexto.  
  
## <a name="return-value"></a>Valor devuelto  
 Si la operación se realiza correctamente, devuelve `S_OK`; de lo contrario, devuelve un código de error. En la tabla siguiente se muestran otros valores posibles.  
  
|Value|Descripción|  
|-----------|-----------------|  
|E_CANNOT_SET_NEXT_STATEMENT_ON_NONLEAF_FRAME|La siguiente instrucción no puede estar en un marco de pila más profundo en la pila de Marcos.|  
|E_CANNOT_SETIP_TO_DIFFERENT_FUNCTION|La siguiente instrucción no está asociada a ningún fotograma de la pila.|  
|E_CANNOT_SET_NEXT_STATEMENT_ON_EXCEPTION|Algunos motores de depuración no pueden establecer la siguiente instrucción después de una excepción.|  
  
## <a name="remarks"></a>Comentarios  
 El puntero de instrucción indica la siguiente instrucción o instrucción que se va a ejecutar. Este método se usa para reintentar una línea de código fuente o para forzar la ejecución para que continúe en otra función, por ejemplo.  
  
## <a name="see-also"></a>Consulte también  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)
