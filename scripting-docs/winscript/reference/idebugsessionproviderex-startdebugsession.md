---
title: IDebugSessionProviderEx:StartDebugSession | Documentos de Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugSessionProviderEx:StartDebugSession
apilocation:
- scrobj.dll
ms.assetid: 247337ca-476c-4aa7-8500-d84fd1d98176
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb120a9acca91014d7b8213a3ed0bd1ab575e118
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62934685"
---
# <a name="idebugsessionproviderexstartdebugsession"></a>IDebugSessionProviderEx:StartDebugSession
Inicia una sesión de depuración con la aplicación especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT StartDebugSession(  
   IRemoteDebugApplication*  pda  
   BOOL  fQuery  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pda`  
 [in] Especifica la aplicación de depuración.  
  
 `fQuery`  
 [in] True indica que una consulta.  
  
## <a name="return-value"></a>Valor devuelto  
 El método devuelve un objeto `HRESULT`. Entre los valores posibles se incluyen los que se indican en la tabla siguiente, entre otros.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`S_OK`|El método se realizó correctamente.|  
  
## <a name="remarks"></a>Comentarios  
 Este método inicia una sesión de depuración con la aplicación especificada. El depurador debe llamar a `IRemoteDebugApplication::ConnectDebugger` antes de abandonar esta llamada.  
  
## <a name="see-also"></a>Vea también  
 [IDebugSessionProviderEx (interfaz)](../../winscript/reference/idebugsessionproviderex-interface.md)   
 [IRemoteDebugApplication::ConnectDebugger](../../winscript/reference/iremotedebugapplication-connectdebugger.md)