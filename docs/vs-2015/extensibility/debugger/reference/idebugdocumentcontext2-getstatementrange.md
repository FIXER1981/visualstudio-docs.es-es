---
title: IDebugDocumentContext2::GetStatementRange | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugDocumentContext2::GetStatementRange
helpviewer_keywords:
- IDebugDocumentContext2::GetStatementRange
ms.assetid: bc94851a-0ec4-47ea-99c7-0a585e54e726
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 68411ac4ded03c83ad0ad1e414107e6591f4e975
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "68145056"
---
# <a name="idebugdocumentcontext2getstatementrange"></a>IDebugDocumentContext2::GetStatementRange
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Obtiene el intervalo de la instrucción de archivo del contexto del documento.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
HRESULT GetStatementRange(   
   TEXT_POSITION* pBegPosition,  
   TEXT_POSITION* pEndPosition  
);  
```  
  
```csharp  
int GetStatementRange(   
   TEXT_POSITION[] pBegPosition,  
   TEXT_POSITION[] pEndPosition  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pBegPosition`  
 [in, out] Un [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) estructura que se rellena con la posición inicial. Establezca este argumento en un valor null si no se necesita esta información.  
  
 `pEndPosition`  
 [in, out] Un [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) estructura que se rellena con la posición final. Establezca este argumento en un valor null si no se necesita esta información.  
  
## <a name="return-value"></a>Valor devuelto  
 Si es correcto, devuelve `S_OK`; en caso contrario, devuelve un código de error.  
  
## <a name="remarks"></a>Comentarios  
 Un intervalo de la instrucción es el intervalo de las líneas que han contribuido el código al que hace referencia este contexto de documento.  
  
 Para obtener el intervalo de código fuente (incluidos los comentarios) en este contexto de documento, llame a la [GetSourceRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getsourcerange.md) método.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo implementar este método para una sencilla `CDebugContext` objeto que expone el [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) interfaz. Este ejemplo se rellena en la posición final sólo si la posición inicial no es un valor null.  
  
```cpp#  
HRESULT CDebugContext::GetStatementRange(TEXT_POSITION* pBegPosition,  
                                         TEXT_POSITION* pEndPosition)    
{    
   HRESULT hr;    
  
   // Check for a valid beginning position argument pointer.    
   if (pBegPosition)    
   {    
      // Copy the member TEXT_POSITION into the local pBegPosition.    
      memcpy(pBegPosition, &m_pos, sizeof (TEXT_POSITION));    
  
      // Check for a valid ending position argument pointer.   
     if (pEndPosition)    
      {    
         // Copy the member TEXT_POSITION into the local pEndPosition.    
         memcpy(pEndPosition, &m_pos, sizeof (TEXT_POSITION));    
      }    
      hr = S_OK;    
   }    
   else    
   {    
      hr = E_INVALIDARG;    
   }    
  
   return hr;    
}    
```  
  
## <a name="see-also"></a>Vea también  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [GetSourceRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getsourcerange.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)
