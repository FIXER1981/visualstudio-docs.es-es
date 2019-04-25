---
title: IEnumDebugProcesses2::Next | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IEnumDebugProcesses2::Next
helpviewer_keywords:
- IEnumDebugProcesses2::Next
ms.assetid: abef89eb-198b-49cd-a4c9-17bce6cac0e1
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 37bf16b49a45b03eee6a1b0abb8af5b719dacff7
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "58987827"
---
# <a name="ienumdebugprocesses2next"></a>IEnumDebugProcesses2::Next
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Devuelve el siguiente conjunto de elementos de la enumeración.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
HRESULT Next(  
   ULONG            celt,  
   IDebugProcess2** rgelt,  
   ULONG*           pceltFetched  
);  
```  
  
```csharp  
int Next(  
   uint             celt,  
   IDebugProcess2[] rgelt,  
   ref uint         pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `celt`  
 [in] El número de elementos que se va a recuperar. También especifica el tamaño máximo de la `rgelt` matriz.  
  
 `rgelt`  
 [in, out] Matriz de [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) elementos que deben rellenarse.  
  
 `pceltFetched`  
 [out] Devuelve el número de elementos realmente devueltos en `rgelt`.  
  
## <a name="return-value"></a>Valor devuelto  
 Si la operación se realiza correctamente, devuelve `S_OK`. Devuelve `S_FALSE` si podrían devolverse un menor que el número solicitado de elementos; de lo contrario, devuelve un código de error.  
  
## <a name="see-also"></a>Vea también  
 [IEnumDebugProcesses2](../../../extensibility/debugger/reference/ienumdebugprocesses2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
