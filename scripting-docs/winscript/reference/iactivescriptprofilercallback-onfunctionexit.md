---
title: IActiveScriptProfilerCallback::OnFunctionExit | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerCallback.OnFunctionExit
apilocation:
- scrobj.dll
ms.assetid: a5d21715-2b0b-423e-8644-f04a9e7cde3d
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9c84b64a12b1a6b61399f70b7209c86dd8d2a9a4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62993337"
---
# <a name="iactivescriptprofilercallbackonfunctionexit"></a>IActiveScriptProfilerCallback::OnFunctionExit
Notifica al analizador de objeto que el motor de scripting termine de ejecutar una función llamada que no es una llamada a Document Object Model (DOM).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT OnFunctionExit(  
    [in] PROFILER_TOKEN scriptId,   
    [in] PROFILER_TOKEN functionId);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `scriptId`  
 [in] El identificador único de la secuencia de comandos que forma parte de la función. Este identificador es asignado por el motor de scripting.  
  
 `functionId`  
 [in] El identificador único de la función. Este identificador es asignado por el motor de scripting.  
  
## <a name="return-value"></a>Valor devuelto  
 Se omite el valor devuelto de este método por el motor de scripting.  
  
## <a name="remarks"></a>Comentarios  
 Para las llamadas de DOM, que llama el motor de scripting [IActiveScriptProfilerCallback2::OnFunctionExitByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionexitbyname.md) en lugar de `IActiveScriptProfilerCallback::OnFunctionExit`. Esto es debido al gran número de métodos únicos y propiedades en el DOM.  
  
## <a name="see-also"></a>Vea también  
 [IActiveScriptProfilerCallback::OnFunctionEnter](../../winscript/reference/iactivescriptprofilercallback-onfunctionenter.md)   
 [IActiveScriptProfilerCallback (Interfaz)](../../winscript/reference/iactivescriptprofilercallback-interface.md)