---
title: IDebugClassField::EnumConstructors | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugClassField::EnumConstructors
helpviewer_keywords:
- IDebugClassField::EnumConstructors method
ms.assetid: 66a250b2-75a0-45aa-8d58-40f91cc4bf7b
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: cd93f4867221f0b42f91fe1f96b8a8b464bf5aa9
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "58997797"
---
# <a name="idebugclassfieldenumconstructors"></a>IDebugClassField::EnumConstructors
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Crea un enumerador para los constructores de esta clase.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
HRESULT EnumConstructors(   
   CONSTRUCTOR_ENUM   cMatch,  
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumConstructors(  
   CONSTRUCTOR_ENUM     cMatch,   
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cMatch`  
 [in] Un valor de la [CONSTRUCTOR_ENUM](../../../extensibility/debugger/reference/constructor-enum.md) enumeración que especifica el tipo de constructores para la enumeración.  
  
 `ppEnum`  
 [out] Devuelve un [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objeto que representa la lista de los constructores. Devuelve un valor null si no hay ningún constructor.  
  
## <a name="return-value"></a>Valor devuelto  
 Si se realiza correctamente, devuelve S_OK o devuelve S_FALSE si no hay ningún constructor. De lo contrario, devuelve un código de error.  
  
## <a name="remarks"></a>Comentarios  
 Cada elemento de la enumeración es un [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md) objeto que describe un método de constructor.  
  
 Normalmente, la lista de los constructores no incluye los constructores predeterminados proporcionados por el compilador.  
  
## <a name="see-also"></a>Vea también  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [CONSTRUCTOR_ENUM](../../../extensibility/debugger/reference/constructor-enum.md)
