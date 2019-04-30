---
title: IActiveScript::GetScriptThreadState | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.GetScriptThreadState
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetScriptThreadState
ms.assetid: 7cac94d0-436e-4c29-895b-0c4afa0b3ccc
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a0066894830c111a8e0ad18f7acdc09d6114162e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62935615"
---
# <a name="iactivescriptgetscriptthreadstate"></a>IActiveScript::GetScriptThreadState
Recupera el estado actual de un subproceso de script.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetScriptThreadState(  
    SCRIPTTHREADID stidThread,    // identifier of script thread  
    SCRIPTTHREADSTATE *pstsState  // receives state flag  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `stidThread`  
 [in] Identificador del subproceso para el que se desea obtener el estado, o uno de los identificadores de subproceso especiales siguientes:  
  
|Valor|Significado|  
|-----------|-------------|  
|SCRIPTTHREADID_BASE|El subproceso base; es decir, se crea una instancia en el subproceso en el que el scripting del motor.|  
|SCRIPTTHREADID_CURRENT|El subproceso actualmente en ejecución.|  
  
 `pstsState`  
 [out] Dirección de una variable que recibe el estado del subproceso indicado. El estado se indica mediante uno de los valores de constantes con nombre definidos por el [SCRIPTTHREADSTATE (enumeración)](../../winscript/reference/scriptthreadstate-enumeration.md) enumeración. Si este parámetro no identifica el subproceso actual, el estado puede cambiar en cualquier momento.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve uno de los siguientes valores:  
  
|Valor devuelto|Significado|  
|------------------|-------------|  
|`S_OK`|Correcto.|  
|`E_POINTER`|Se especificó un puntero no válido.|  
|`E_UNEXPECTED`|No se esperaba la llamada (por ejemplo, el motor de scripting no se ha cargado o inicializado).|  
  
## <a name="remarks"></a>Comentarios  
 Este método se pueda llamar desde subprocesos no son de base sin resultante en una llamada que no sea de base a los objetos de host o a la [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) interfaz.  
  
## <a name="see-also"></a>Vea también  
 [IActiveScript](../../winscript/reference/iactivescript.md)