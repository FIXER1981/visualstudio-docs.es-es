---
title: Implementación de ejemplo de variables locales | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], local variables
- expression evaluation, local variables
ms.assetid: 66a2e00a-f558-4e87-96b8-5ecf5509e04c
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6e943fd7ba27fe21029bab4d818803186147476e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "65704886"
---
# <a name="sample-implementation-of-locals"></a>Implementación de ejemplo de variables locales
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

> [!IMPORTANT]
> En Visual Studio 2015, esta manera de implementar evaluadores de expresiones está en desuso. Para obtener información sobre la implementación de evaluadores de expresiones CLR, consulte [evaluadores](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) de expresiones CLR y [ejemplo de evaluador de expresiones administradas](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Aquí se proporciona información general sobre cómo Visual Studio obtiene las variables locales para un método del evaluador de expresiones (EE):  
  
1. Visual Studio llama al método (DE) [getdebugproperty (](../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md) del motor de depuración para obtener un objeto [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) que representa todas las propiedades del marco de pila, incluidas las variables locales.  
  
2. `IDebugStackFrame2::GetDebugProperty` llama a [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) para obtener un objeto que describe el método en el que se produjo el punto de interrupción. El DE proporciona un proveedor de símbolos ([IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)), una dirección ([IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)) y un enlazador ([IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)).  
  
3. `IDebugExpressionEvaluator::GetMethodProperty` llama a [GetContainerField](../../extensibility/debugger/reference/idebugsymbolprovider-getcontainerfield.md) con el `IDebugAddress` objeto proporcionado para obtener un [IDebugContainerField](../../extensibility/debugger/reference/idebugcontainerfield.md) que representa el método que contiene la dirección especificada.  
  
4. La `IDebugContainerField` interfaz se consulta para la interfaz [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) . Es esta interfaz que proporciona acceso a las variables locales del método.  
  
5. `IDebugExpressionEvaluator::GetMethodProperty` crea una instancia de una clase (llamada `CFieldProperty` en el ejemplo) que implementa la `IDebugProperty2` interfaz para representar las variables locales del método. El `IDebugMethodField` objeto se coloca en este `CFieldProperty` objeto junto con los `IDebugSymbolProvider` `IDebugAddress` objetos, y `IDebugBinder` .  
  
6. Cuando `CFieldProperty` se inicializa el objeto, se llama a [GetInfo](../../extensibility/debugger/reference/idebugfield-getinfo.md) en el `IDebugMethodField` objeto para obtener una estructura [FIELD_INFO](../../extensibility/debugger/reference/field-info.md) que contenga toda la información que se pueda mostrar sobre el propio método.  
  
7. `IDebugExpressionEvaluator::GetMethodProperty` Devuelve el `CFieldProperty` objeto como un `IDebugProperty2` objeto.  
  
8. Visual Studio llama a [EnumChildren](../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) en el `IDebugProperty2` objeto devuelto con el filtro `guidFilterLocalsPlusArgs` . Esto devuelve un objeto [IEnumDebugPropertyInfo2](../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) que contiene las variables locales del método. Esta enumeración se rellena mediante llamadas a [EnumLocals](../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md) y [EnumArguments](../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md).  
  
9. Visual Studio llama a [Next](../../extensibility/debugger/reference/ienumdebugpropertyinfo2-next.md) para obtener una estructura de [DEBUG_PROPERTY_INFO](../../extensibility/debugger/reference/debug-property-info.md) para cada local. Esta estructura contiene un puntero a una `IDebugProperty2` interfaz para un local.  
  
10. Visual Studio llama a [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) para cada local para obtener el nombre, el valor y el tipo de la configuración regional. Esta es la información que se muestra en la ventana **variables locales** .  
  
## <a name="in-this-section"></a>En esta sección  
 [Implementación de GetMethodProperty](../../extensibility/debugger/implementing-getmethodproperty.md)  
 Describe una implementación de [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md).  
  
 [Enumeración de variables locales](../../extensibility/debugger/enumerating-locals.md)  
 Describe cómo el motor DE depuración (DE) realiza una llamada para enumerar los argumentos o variables locales.  
  
 [Obtención de propiedades locales](../../extensibility/debugger/getting-local-properties.md)  
 Describe cómo realiza una llamada para obtener el nombre, el tipo y el valor de una o más variables locales.  
  
 [Obtención de valores locales](../../extensibility/debugger/getting-local-values.md)  
 Describe cómo obtener el valor de la variable local, que requiere los servicios de un objeto de enlazador proporcionado por el contexto de evaluación.  
  
 [Evaluación de variables locales](../../extensibility/debugger/evaluating-locals.md)  
 Explica cómo se evalúan las variables locales.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Contexto de evaluación](../../extensibility/debugger/evaluation-context.md)  
 Proporciona los argumentos que se pasan cuando el método llama al evaluador DE expresiones (EE).  
  
 [Ejemplo de MyCEE](https://msdn.microsoft.com/624a018b-9179-402f-9d48-3aec87b48f4f)  
 Muestra un enfoque de implementación para crear un evaluador de expresiones para el lenguaje MyC.  
  
## <a name="see-also"></a>Consulte también  
 [Visualización de variables locales](../../extensibility/debugger/displaying-locals.md)
