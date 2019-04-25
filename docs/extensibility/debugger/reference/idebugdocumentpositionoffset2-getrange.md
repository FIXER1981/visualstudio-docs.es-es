---
title: IDebugDocumentPositionOffset2::GetRange | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentPositionOffset2::GetRange
ms.assetid: 27da7130-0932-4f97-abde-05e6fb018606
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e8b309af47aed94c45eca418b390be041f66f609
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686917"
---
# <a name="idebugdocumentpositionoffset2getrange"></a>IDebugDocumentPositionOffset2::GetRange
Recupera el intervalo para la posición del documento actual.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetRange(
   DWORD* pdwBegOffset,
   DWORD* pdwEndOffset
);
```

```csharp
public int GetRange(
   ref uint pdwBegOffset,
   ref uint pdwEndOffset
);
```

#### <a name="parameters"></a>Parámetros
 `pdwBegOffset`

 [in, out] Desplazamiento de la posición inicial del intervalo. Establezca este parámetro en un valor null si no se necesita esta información.

 `pdwEndOffset`

 [in, out] Desplazamiento de la posición final del intervalo. Establezca este parámetro en un valor null si no se necesita esta información.

## <a name="return-value"></a>Valor devuelto
 Si es correcto, devuelve `S_OK`; en caso contrario, devuelve un código de error.

## <a name="remarks"></a>Comentarios
 El intervalo especificado en una posición de documento para un punto de interrupción se utiliza el motor de depuración (DE) para buscar directamente una instrucción que contribuye realmente el código. Por ejemplo, considere el siguiente código:

```
Line 5: // comment
Line 6: x = 1;
```

 Línea 5 no contribuye con ningún código para el programa que se está depurando. Si desea que el depurador, que establece el punto de interrupción en la línea 5 la DE buscar hacia delante de una determinada cantidad de la primera línea que contribuye de código, el depurador especificaría un rango que incluya las líneas de candidato adicional donde se puede colocar correctamente un punto de interrupción. La DE, a continuación, podría buscar hacia delante a través de esas líneas hasta que encuentra una línea que pudiera aceptar un punto de interrupción.

## <a name="see-also"></a>Vea también
- [IDebugDocumentPositionOffset2](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2.md)
- [GetRange](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)