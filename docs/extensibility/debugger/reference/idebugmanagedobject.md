---
title: IDebugManagedObject | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugManagedObject
helpviewer_keywords:
- IDebugManagedObject interface
ms.assetid: 3ae09d34-112c-4285-80ee-9f7f8dc414d7
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6fbd270aa1b65f05f308d41d22f154fb53b8833d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80727689"
---
# <a name="idebugmanagedobject"></a>IDebugManagedObject
> [!IMPORTANT]
> En Visual Studio 2015, esta manera de implementar evaluadores de expresiones está en desuso. Para obtener información sobre la implementación de evaluadores de expresiones CLR, consulte [evaluadores](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) de expresiones CLR y [ejemplo de evaluador de expresiones administradas](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Esta interfaz permite al evaluador de expresiones (EE) llamar a propiedades o métodos en instancias de clase de valor (por ejemplo, `System.Decimal` ) y establecer su valor sin llamar a [Evaluate](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md) en el programa que se está depurando.

## <a name="syntax"></a>Sintaxis

```
IDebugManagedObject : IDebugObject
```

## <a name="notes-for-implementers"></a>Notas para los implementadores
 Un evaluador de expresiones implementa esta interfaz para representar un objeto de código administrado como una variable.

## <a name="notes-for-callers"></a>Notas para llamadores
 Para obtener esta interfaz, llame a [GetManagedDebugObject](../../../extensibility/debugger/reference/idebugobject-getmanageddebugobject.md) en un [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) que represente una instancia de una clase de valor.

## <a name="methods-in-vtable-order"></a>Métodos en orden de Vtable
 Además de los métodos heredados de [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md), la `IDebugManagedObject` interfaz expone los métodos siguientes.

|Método|Descripción|
|------------|-----------------|
|[GetManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject-getmanagedobject.md)|Devuelve una interfaz que representa el objeto de código administrado y desde el que se puede obtener cualquier interfaz de código administrado adecuada.|
|[SetFromManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject-setfrommanagedobject.md)|Establece el valor de este objeto en el valor de un objeto de código administrado especificado.|

## <a name="remarks"></a>Observaciones
 Un evaluador de expresiones utiliza esta interfaz para almacenar un objeto de código administrado en un árbol de análisis.

## <a name="requirements"></a>Requisitos
 Encabezado: EE. h

 Espacio de nombres: Microsoft. VisualStudio. Debugger. Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [Interfaces de evaluación de expresiones](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [Evaluate](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md)
