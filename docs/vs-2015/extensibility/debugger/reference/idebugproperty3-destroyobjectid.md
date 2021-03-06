---
title: IDebugProperty3::D estroyObjectID | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProperty3::DestroyObjectID
helpviewer_keywords:
- IDebugProperty3::DestroyObjectID
ms.assetid: bd08f356-cc67-4717-98c9-c3d00cad2040
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 3a610cd5c947d77048e86b31c92298f6cc18607d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68193421"
---
# <a name="idebugproperty3destroyobjectid"></a>IDebugProperty3::DestroyObjectID
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Destruye el identificador único asociado a esta propiedad, que indica que el autor de la llamada ya no le importa que identifique esta propiedad de forma única desde todas las demás propiedades.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DestroyObjectID(  
   void  
);  
```  
  
```csharp  
int DestroyObjectID();  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Si la operación se realiza correctamente, devuelve `S_OK`; de lo contrario, devuelve un código de error.  
  
## <a name="remarks"></a>Observaciones  
 Si el motor de depuración no necesita admitir identificadores únicos para una propiedad (porque ya realiza un seguimiento de ellos de forma exclusiva), puede devolver simplemente `E_NOTIMPL` para este método.  
  
 Los identificadores únicos se crean con una llamada al método [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md) cuando el llamador desea asegurarse de que esta propiedad se identifica de forma única entre todas las demás propiedades.  
  
## <a name="see-also"></a>Consulte también  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)
