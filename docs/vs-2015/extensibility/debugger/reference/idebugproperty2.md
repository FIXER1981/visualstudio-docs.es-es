---
title: IDebugProperty2 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProperty2
helpviewer_keywords:
- IDebugProperty2 interface
ms.assetid: a7d5c70f-a1a5-4120-9f70-184e01c25bff
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 1f72a66e6dbfe2749910019760c16f6363498785
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "90842739"
---
# <a name="idebugproperty2"></a>IDebugProperty2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Esta interfaz representa una propiedad de marco de pila, una propiedad de documento de programa u otra propiedad. La propiedad suele ser el resultado de una evaluación de expresión.  
  
> [!NOTE]
> Este uso de "propiedad" no se debe confundir con, lo que significa una variable miembro de una clase, aunque un `IDebugProperty2` puede representar tal entidad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
IDebugProperty2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Notas para los implementadores  
 El DE implementa esta interfaz para representar un tipo determinado de valor. Por ejemplo, el valor podría ser un valor numérico como resultado de una evaluación de expresión, un contexto de memoria utilizado para mostrar memoria o una lista de registros y sus valores.  
  
## <a name="notes-for-callers"></a>Notas para llamadores  
 Llame a [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) o [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) para obtener esta interfaz, que representa el resultado de una evaluación. `IDebugExpression2::EvaluateAsync` devuelve esta interfaz mediante el envío de una interfaz [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) al SDM, que a su vez llama a [GetResult](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md) para recuperar la propiedad.  
  
 [Getdebugproperty (](../../../extensibility/debugger/reference/idebugpropertycreateevent2-getdebugproperty.md) devuelve esta interfaz para proporcionar el documento de script asociado.  
  
 [GetReturnValue](../../../extensibility/debugger/reference/idebugreturnvalueevent2-getreturnvalue.md) devuelve esta interfaz para representar el valor devuelto de una función.  
  
 [Getdebugproperty (](../../../extensibility/debugger/reference/idebugprogram2-getdebugproperty.md) devuelve esta interfaz para representar varias propiedades del programa, como un nombre o un contexto de memoria.  
  
 [Getdebugproperty (](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md) devuelve esta interfaz para representar varias propiedades del marco de pila, como las variables locales.  
  
## <a name="methods-in-vtable-order"></a>Métodos en orden de Vtable  
 En la tabla siguiente se muestran los métodos de `IDebugProperty2` .  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)|Rellena una estructura de [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) que describe una propiedad.|  
|[SetValueAsString](../../../extensibility/debugger/reference/idebugproperty2-setvalueasstring.md)|Establece el valor de una propiedad de una cadena.|  
|[SetValueAsReference](../../../extensibility/debugger/reference/idebugproperty2-setvalueasreference.md)|Establece el valor de la propiedad a partir del valor de una referencia determinada.|  
|[EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)|Enumera los elementos secundarios de una propiedad.|  
|[GetParent](../../../extensibility/debugger/reference/idebugproperty2-getparent.md)|Devuelve el elemento primario de una propiedad.|  
|[GetDerivedMostProperty](../../../extensibility/debugger/reference/idebugproperty2-getderivedmostproperty.md)|Devuelve la propiedad que describe la propiedad más derivada de una propiedad.|  
|[GetMemoryBytes](../../../extensibility/debugger/reference/idebugproperty2-getmemorybytes.md)|Devuelve los bytes de memoria que componen el valor de una propiedad.|  
|[GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md)|Devuelve el contexto de memoria para un valor de propiedad.|  
|[GetSize](../../../extensibility/debugger/reference/idebugproperty2-getsize.md)|Devuelve el tamaño, en bytes, del valor de propiedad.|  
|[GetReference](../../../extensibility/debugger/reference/idebugproperty2-getreference.md)|Devuelve una referencia al valor de esta propiedad.|  
|[GetExtendedInfo](../../../extensibility/debugger/reference/idebugproperty2-getextendedinfo.md)|Devuelve la información extendida de una propiedad.|  
  
## <a name="remarks"></a>Notas  
 Una propiedad, como se representa mediante una `IDebugProperty2` interfaz, puede considerarse como un valor con un nombre, un tipo y una dirección. En términos más generales, `IDebugProperty2` puede representar cualquier elemento que tenga una estructura jerárquica, con nodos primarios y secundarios.  
  
 Una propiedad suele ser transitoria y dura solo mientras el marco de pila actual, por ejemplo. Por otro lado, una referencia, como se representa mediante una interfaz [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) , dura siempre que el valor permanezca en la memoria.  
  
 El IDE puede usar la `IDebugProperty2` interfaz para permitir que los usuarios examinen y modifiquen las propiedades en tiempo de ejecución.  
  
## <a name="requirements"></a>Requisitos  
 Encabezado: msdbg. h  
  
 Espacio de nombres: Microsoft. VisualStudio. Debugger. Interop  
  
 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Consulte también  
 [Interfaces principales](../../../extensibility/debugger/reference/core-interfaces.md)   
 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
