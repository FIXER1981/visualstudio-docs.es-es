---
title: 'IDebugCustomAttributeQuery2:: Enumcustomattributes (| Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugCustomAttributeQuery2::EnumCustomAttributes
helpviewer_keywords:
- IDebugCustomAttributeQuery2::EnumCustomAttributes
ms.assetid: 94bfce74-aa3d-45f0-8e04-5715faf85217
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: b09285b2fbab65321d0949be7fbd9c7a03c54ed3
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "62568413"
---
# <a name="idebugcustomattributequery2enumcustomattributes"></a>IDebugCustomAttributeQuery2::EnumCustomAttributes
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Obtiene un enumerador para todos los atributos personalizados asociados a este campo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
HRESULT EnumCustomAttributes(   
   IEnumDebugCustomAttributes** ppEnum  
);  
```  
  
```csharp  
int EnumCustomAttributes(  
   out IEnumDebugCustomAttributes ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppEnum`  
 enuncia Devuelve un objeto [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md) que representa la lista de atributos personalizados; de lo contrario, devuelve un valor NULL si no hay ningún atributo personalizado.  
  
## <a name="return-value"></a>Valor devuelto  
 Si es correcto, Devuelve S_OK o S_FALSE si no hay ningún atributo personalizado en este campo. De lo contrario, devuelve un código de error.  
  
## <a name="remarks"></a>Comentarios  
 Un campo puede tener varios atributos personalizados.  
  
## <a name="see-also"></a>Consulte también  
 [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)   
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)
