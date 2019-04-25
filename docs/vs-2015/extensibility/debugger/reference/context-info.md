---
title: CONTEXT_INFO | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- CONTEXT_INFO
helpviewer_keywords:
- CONTEXT_INFO structure
ms.assetid: 6b513f4e-e7b0-4969-adf0-2205ccc1e09b
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f4e8c1b438cd2fa2721e81f055695e5836c26d12
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "58998319"
---
# <a name="contextinfo"></a>CONTEXT_INFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Esta estructura describe un contexto de la memoria o el contexto del código.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
typedef struct _tagCONTEXT_INFO {   
   CONTEXT_INFO_FIELDS dwFields;  
   BSTR                bstrModuleUrl;  
   BSTR                bstrFunction;  
   TEXT_POSITION       posFunctionOffset;  
   BSTR                bstrAddress;  
   BSTR                bstrAddressOffset;  
   BSTR                bstrAddressAbsolute;  
} CONTEXT_INFO;  
```  
  
```csharp  
public struct CONTEXT_INFO {  
   public uint          dwFields;  
   public string        bstrModuleUrl;  
   public string        bstrFunction;  
   public TEXT_POSITION posFunctionOffset;  
   public string        bstrAddress;  
   public string        bstrAddressOffset;  
   public string        bstrAddressAbsolute;  
};  
```  
  
## <a name="members"></a>Miembros  
 dwFields  
 Una combinación de marcas de él [CONTEXT_INFO_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md) enumeración que especifica qué campos se rellenan<strong>.</strong>  
  
 bstrModuleUrl  
 El nombre del módulo donde se encuentra el contexto.  
  
 bstrFunction  
 El nombre de la función donde se encuentra el contexto.  
  
 posFunctionOffset  
 Un [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) estructura que identifica el desplazamiento de línea y columna de la función asociada al contexto del código.  
  
 bstrAddress  
 La dirección en el código donde se encuentra el contexto especificado.  
  
 bstrAddressOffset  
 El desplazamiento de la dirección en el código donde se encuentra el contexto especificado.  
  
 bstrAddressAbsolute  
 La dirección absoluta en la memoria donde se encuentra el contexto especificado.  
  
## <a name="remarks"></a>Comentarios  
 Esta estructura se devuelve desde una llamada a la [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md) método.  
  
 Un uso típico de esta estructura es de apoyo un **memoria** ventana de depuración.  
  
## <a name="requirements"></a>Requisitos  
 Encabezado: msdbg.h  
  
 Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop  
  
 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Vea también  
 [Estructuras y uniones](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)   
 [CONTEXT_INFO_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)
