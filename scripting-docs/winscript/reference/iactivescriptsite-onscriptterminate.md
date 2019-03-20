---
title: IActiveScriptSite::OnScriptTerminate | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.OnScriptTerminate
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_OnScriptTerminate
ms.assetid: 3301ddf4-5929-404c-81d3-1a720e589008
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 664f974b26a2cae0d1e16d37dc3bc66e95993d6f
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "58144828"
---
# <a name="iactivescriptsiteonscriptterminate"></a>IActiveScriptSite::OnScriptTerminate
Informa al host que ha completado la secuencia de comandos de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT OnScriptTerminate(  
    VARIANT *pvarResult,   // address of script results  
    EXCEPINFO *pexcepinfo  // address of structure with exception information  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pvarResult`  
 [in] Dirección de una variable que contiene el resultado de la secuencia de comandos, o `NULL` si el script genera ningún resultado.  
  
 `pexcepinfo`  
 [in] Dirección de un `EXCEPINFO` estructura que contiene información de excepción generada cuando finaliza la secuencia de comandos, o `NULL` si se ha generado ninguna excepción.  
  
## <a name="return-value"></a>Valor devuelto  
 Si la operación se realiza correctamente, devuelve `S_OK`.  
  
## <a name="remarks"></a>Comentarios  
 El motor de scripting llama a este método antes de llamar a la [IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md) método con la marca SCRIPTSTATE_INITIALIZED establecida, se completa. Este método puede utilizarse para devolver el estado de finalización y los resultados al host. Tenga en cuenta que muchos lenguajes de secuencia de comandos, que se basan en recibir eventos desde el host, tienen intervalos de vida definidos por el host. En este caso, es posible que nunca se llama a este método.  
  
## <a name="see-also"></a>Vea también  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)