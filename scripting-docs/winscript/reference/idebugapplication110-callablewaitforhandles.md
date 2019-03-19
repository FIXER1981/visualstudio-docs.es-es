---
title: IDebugApplication110::CallableWaitForHandles | Documentos de Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplication110::CallableWaitForHandles
ms.assetid: 02e79b60-0d67-47f9-bf78-b65a02c9c014
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ac5482924288e52895398084aa4f5ab44e151a66
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "58155375"
---
# <a name="idebugapplication110callablewaitforhandles"></a>IDebugApplication110::CallableWaitForHandles
Espera a que cualquiera de los identificadores especificados que se señalen al tiempo que permite las llamadas entre subprocesos se publicarán en este subproceso. Este método debe llamarse desde el subproceso del depurador.  
  
> [!IMPORTANT]
>  [IDebugApplication110 (interfaz)](../../winscript/reference/idebugapplication110-interface.md) es implementada por PDM v11.0 y versiones posteriores. Se encuentra en activdbg100.h.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CallableWaitForHandles([in] DWORD handleCount, [in, size_is(handleCount)] const HANDLE* pHandles, [out] DWORD* pIndex);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `handleCount`  
 El número de identificadores para esperar.  
  
 `pHandles`  
 El conjunto de identificadores de espera.  
  
 `pIndex`  
 Cuando el valor HRESULT es S_OK, el índice en `pHandles` para el identificador que fue señalado.  
  
## <a name="see-also"></a>Vea también  
 [IDebugApplication110 (Interfaz)](../../winscript/reference/idebugapplication110-interface.md)