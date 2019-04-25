---
title: IDebugParsedExpression::EvaluateSync | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugParsedExpression::EvaluateSync
helpviewer_keywords:
- IDebugParsedExpression::EvaluateSync method
ms.assetid: 0ea04cfa-de87-4b6c-897e-4572c1a28942
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ea659b847149a6abb2c3a5ba7cc947a59c7ae41c
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56709647"
---
# <a name="idebugparsedexpressionevaluatesync"></a>IDebugParsedExpression::EvaluateSync
Este método evalúa la expresión analizada y, opcionalmente, convierte el resultado a otro tipo de datos.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT EvaluateSync( 
   DWORD                 dwEvalFlags,
   DWORD                 dwTimeout,
   IDebugSymbolProvider* pSymbolProvider,
   IDebugAddress*        pAddress,
   IDebugBinder*         pBinder,
   BSTR                  bstrResultType,
   IDebugProperty2**     ppResult
);
```

```csharp
int EvaluateSync(
   uint                 dwEvalFlags,
   uint                 dwTimeout,
   IDebugSymbolProvider pSymbolProvider,
   IDebugAddress        pAddress,
   IDebugBinder         pBinder,
   string               bstrResultType,
   out IDebugProperty2  ppResult
);
```

#### <a name="parameters"></a>Parámetros
 `dwEvalFlags`

 [in] Una combinación de [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) constantes que controlan cómo se puede evaluar la expresión.

 `dwTimeout`

 [in] Especifica el tiempo máximo, en milisegundos para esperar antes de volver de este método. Use `INFINITE` para esperar indefinidamente.

 `pSymbolProvider`

 [in] El proveedor de símbolos, expresado como un [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) interfaz.

 `pAddress`

 [in] La ubicación de ejecución actual dentro de un método, expresado como un [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) interfaz.

 `pBinder`

 [in] El enlazador, expresado como un [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) interfaz.

 `bstrResultType`

 [in] El tipo de resultado debe convertirse. Este argumento puede ser un valor null.

 `ppResult`

 [out] Devuelve el [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) interfaz que representa los resultados de evaluación.

## <a name="return-value"></a>Valor devuelto
 Si es correcto, devuelve `S_OK`; en caso contrario, devuelve un código de error.

## <a name="remarks"></a>Comentarios
 El contexto de evaluación de expresión viene dado por `pAddress`, lo que hace posible determinar el método contenedor y, a continuación, el ámbito del idioma de uso de reglas para determinar el valor de los símbolos en la expresión.

## <a name="see-also"></a>Vea también
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)
- [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)
- [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)