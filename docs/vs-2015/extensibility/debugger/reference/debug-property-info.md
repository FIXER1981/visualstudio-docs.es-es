---
title: DEBUG_PROPERTY_INFO | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- DEBUG_PROPERTY_INFO
helpviewer_keywords:
- DEBUG_PROPERTY_INFO structure
ms.assetid: 5a085d18-62c6-4740-b9e9-3f5db6bfdf7f
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4c4200cb5a44e185d50158829fe44152707ee459
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68143043"
---
# <a name="debug_property_info"></a>DEBUG_PROPERTY_INFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Contiene información sobre una propiedad de depuración.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
typedef struct tagDEBUG_PROPERTY_INFO {   
   DEBUGPROP_INFO_FLAGS dwValidFields;  
   BSTR                 bstrFullName;  
   BSTR                 bstrName;  
   BSTR                 bstrType;  
   BSTR                 bstrValue;  
   IDebugProperty2*     pProperty;  
   DBG_ATTRIB_FLAGS     dwAttrib;  
} DEBUG_PROPERTY_INFO;  
```  
  
```csharp  
public struct DEBUG_PROPERTY_INFO {   
   public uint            dwValidFields;  
   public string          bstrFullName;  
   public string          bstrName;  
   public string          bstrType;  
   public string          bstrValue;  
   public IDebugProperty2 pProperty;  
   public ulong           dwAttrib;  
};  
```  
  
## <a name="members"></a>Miembros  
 dwValidFields  
 Combinación de marcas de la enumeración [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) que especifica qué campos se rellenan.  
  
 bstrFullName  
 Nombre completo de la propiedad.  
  
 bstrName  
 Nombre de la propiedad dentro de un contexto.  
  
 bstrType  
 El tipo de propiedad como una cadena con formato.  
  
 bstrValue  
 Valor de la propiedad como una cadena con formato.  
  
 pProperty  
 Objeto [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) descrito por esta estructura.  
  
 dwAttrib  
 Combinación de marcas de la enumeración [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) que describe los atributos de esta propiedad.  
  
## <a name="remarks"></a>Comentarios  
 Una propiedad es un objeto de una naturaleza jerárquica que tiene un nombre, un tipo y un valor. Por ejemplo, una propiedad puede describir las variables locales, los parámetros, las variables y las expresiones de inspección y los registros.  
  
 Esta estructura se pasa al método [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) donde se rellena. Esta estructura también se devuelve como parte de una lista de esta estructura de la interfaz [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) que, a su vez, se devuelve de una llamada a los métodos [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) y [EnumProperties (](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md) .  
  
## <a name="requirements"></a>Requisitos  
 Encabezado: msdbg. h  
  
 Espacio de nombres: Microsoft. VisualStudio. Debugger. Interop  
  
 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Consulte también  
 [Estructuras y uniones](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)   
 [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)   
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)   
 [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)
