---
title: 'IDebugProgram2:: Attach | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProgram2::Attach
helpviewer_keywords:
- IDebugProgram2::Attach
ms.assetid: de069fbf-a565-4905-b102-f5658c55aacd
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0e029c2e16d5eee1764b463b21fc0fd8a4032252
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "62580409"
---
# <a name="idebugprogram2attach"></a>IDebugProgram2::Attach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Se asocia al programa.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
HRESULT Attach(   
   IDebugEventCallback2* pCallback  
);  
```  
  
```csharp  
int Attach(   
   IDebugEventCallback2 pCallback  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pCallback`  
 de Objeto [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) que se va a usar para la notificación de eventos de depuración.  
  
## <a name="return-value"></a>Valor devuelto  
 Si la operación se realiza correctamente, devuelve `S_OK`; de lo contrario, devuelve un código de error. En la tabla siguiente se muestran algunos códigos de error posibles.  
  
|Value|Descripción|  
|-----------|-----------------|  
|`E_ATTACH_DEBUGGER_ALREADY_ATTACHED`|El programa especificado ya está asociado al depurador.|  
|`E_ATTACH_DEBUGGEE_PROCESS_SECURITY_VIOLATION`|Se ha producido una infracción de seguridad durante el procedimiento de asociación.|  
|`E_ATTACH_CANNOT_ATTACH_TO_DESKTOP`|No se puede adjuntar un programa de escritorio al depurador.|  
  
## <a name="remarks"></a>Comentarios  
 Un motor DE depuración (DE) nunca llama a este método para asociar a un programa. Si el DE se ejecuta en el espacio de direcciones del programa, se llama al método [alattach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) . Si el DE se ejecuta en el espacio de direcciones del administrador de depuración de la sesión (SDM), se llama al método [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) .  
  
## <a name="see-also"></a>Consulte también  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [Conectar](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)   
 [Adjuntar](../../../extensibility/debugger/reference/idebugengine2-attach.md)
