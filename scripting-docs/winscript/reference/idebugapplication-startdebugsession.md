---
title: IDebugApplication::StartDebugSession | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.StartDebugSession
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::StartDebugSession
ms.assetid: 737f8424-bbcf-473f-9cf1-6601b9aa250d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a42fe61d67eedbe6f69350c7b5ec17726f43486e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62990693"
---
# <a name="idebugapplicationstartdebugsession"></a>IDebugApplication::StartDebugSession
Se inicia el entorno de desarrollo integrado de depurador predeterminado (IDE) y se adjunta una sesión de depuración para esta aplicación, si uno no está ya conectado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT StartDebugSession();  
```  
  
#### <a name="parameters"></a>Parámetros  
 Este método no toma ningún parámetro.  
  
## <a name="return-value"></a>Valor devuelto  
 El método devuelve un objeto `HRESULT`. Entre los valores posibles se incluyen los que se indican en la tabla siguiente, entre otros.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`S_OK`|El método se realizó correctamente.|  
  
## <a name="remarks"></a>Comentarios  
 Este método se utiliza para implementar la depuración just-in-time.  
  
## <a name="see-also"></a>Vea también  
 [IDebugApplication (Interfaz)](../../winscript/reference/idebugapplication-interface.md)