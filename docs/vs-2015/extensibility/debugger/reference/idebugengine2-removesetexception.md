---
title: 'IDebugEngine2:: RemoveSetException | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugEngine2::RemoveSetException
helpviewer_keywords:
- IDebugEngine2::RemoveSetException
ms.assetid: bdd25097-0e9d-4218-b417-0497ea48d2e8
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 53ba8c9c1934ee1c036e14fb51abd5babcf7e4c5
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68195963"
---
# <a name="idebugengine2removesetexception"></a>IDebugEngine2::RemoveSetException
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Quita la excepción especificada para que el motor de depuración ya no la administre.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
HRESULT RemoveSetException(   
   EXCEPTION_INFO* pException  
);  
```  
  
```csharp  
int RemoveSetException(   
   EXCEPTION_INFO[] pException  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pException`  
 de Estructura [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) que describe la excepción que se va a quitar.  
  
## <a name="return-value"></a>Valor devuelto  
 Si la operación se realiza correctamente, devuelve `S_OK`; de lo contrario, devuelve un código de error.  
  
## <a name="remarks"></a>Comentarios  
 La excepción que se va a quitar se debe haber establecido previamente mediante una llamada anterior al método [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md) .  
  
 Para quitar todas las excepciones set a la vez, llame al método [RemoveAllSetExceptions](../../../extensibility/debugger/reference/idebugengine2-removeallsetexceptions.md) .  
  
## <a name="see-also"></a>Consulte también  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)
