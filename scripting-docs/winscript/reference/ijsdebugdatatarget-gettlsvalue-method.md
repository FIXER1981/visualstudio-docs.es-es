---
title: Método Ijsdebugdatatarget | Documentos de Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugDataTarget.GetTlsValue
apilocation:
- jscript9diag.dll
ms.assetid: db575be9-7b24-45c5-9008-e4f2f76d6757
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 458aaab05f274983fdaf69c6e702502974665403
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "58157206"
---
# <a name="ijsdebugdatatargetgettlsvalue-method"></a>IJsDebugDataTarget::GetTlsValue (Método)
Para el subproceso que se está depurando, recupera el valor en la ranura de subproceso (TLS) de almacenamiento local para el índice especificado de TLS.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetTlsValue(  
   DWORD threadId,  
   UINT32 tlsIndex,  
   UINT64 *pValue  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `threadId`  
 [in] Que se ejecuta en el proceso de destino para leer desde el subproceso.  
  
 `tlsIndex`  
 [in] El índice TLS que se asignó cuando el proceso de destino llama a la función TlsAlloc.  
  
 `pValue`  
 [out] El valor dimensionado por puntero que se almacena en la ranura TLS de subprocesos. Si el subproceso de destino es de 32 bits, los 32 bits superiores de este valor será cero.  
  
## <a name="return-value"></a>Valor devuelto  
  
## <a name="remarks"></a>Comentarios  
 Cada subproceso de un proceso tiene su propia ranura para cada índice TLS.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** jscript9diag.h  
  
## <a name="see-also"></a>Vea también  
 [IJsDebugDataTarget (Interfaz)](../../winscript/reference/ijsdebugdatatarget-interface.md)