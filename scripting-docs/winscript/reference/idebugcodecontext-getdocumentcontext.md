---
title: IDebugCodeContext::GetDocumentContext | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugCodeContext.GetDocumentContext
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugCodeContext::GetDocumentContext
ms.assetid: 9fe17b65-3a8c-4d21-9b66-0e4ff303af72
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 48c707432ddb94fae111c971b89c8ff74f34ac21
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62974546"
---
# <a name="idebugcodecontextgetdocumentcontext"></a>IDebugCodeContext::GetDocumentContext
Devuelve el contexto de documento asociado a este contexto de código.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetDocumentContext(  
   IDebugDocumentContext**  ppsc  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppsc`  
 [out] El contexto de documento asociado a este contexto de código.  
  
## <a name="return-value"></a>Valor devuelto  
 El método devuelve un objeto `HRESULT`. Entre los valores posibles se incluyen los que se indican en la tabla siguiente, entre otros.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`S_OK`|El método se realizó correctamente.|  
  
## <a name="remarks"></a>Comentarios  
 Para los documentos de texto, el intervalo de la posición del carácter debe incluir el texto de toda la instrucción. Esto permite al depurador IDE para resaltar la instrucción de código fuente actual.  
  
## <a name="see-also"></a>Vea también  
 [IDebugCodeContext (Interfaz)](../../winscript/reference/idebugcodecontext-interface.md)