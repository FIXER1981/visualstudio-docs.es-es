---
title: IDebugArrayObject2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugArrayObject2 interface
ms.assetid: be6e504d-4ab3-4141-a61b-0953ee0e038e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 89130c43e38bc53e0efeb93325df94e7076d9ef1
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56691961"
---
# <a name="idebugarrayobject2"></a>IDebugArrayObject2
> [!IMPORTANT]
>  En Visual Studio 2015, esta forma de implementar los evaluadores de expresión está en desuso. Para obtener información sobre la implementación de evaluadores de expresión de CLR, vea [evaluadores de expresiones CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) y [Managed expresión del evaluador de expresiones Sample](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Representa un objeto de matriz administrada y permite que un evaluador de expresiones (EE) para determinar el índice de base (límites inferiores) de la matriz.

## <a name="syntax"></a>Sintaxis

```
IDebugArrayObject2 : IDebugArrayObject
```

## <a name="notes-for-implementers"></a>Notas para los implementadores
 Esto se implementa mediante el motor de depuración administrado (DE).

## <a name="methods"></a>Métodos
 Además de los métodos en el [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md) interfaz, esta interfaz implementa los métodos siguientes:

|Método|Descripción|
|------------|-----------------|
|[GetBaseIndices](../../../extensibility/debugger/reference/idebugarrayobject2-getbaseindices.md)|Recupera los índices de bases (límites inferiores) para cada índice dado el número de dimensiones de la matriz.|
|[HasBaseIndices](../../../extensibility/debugger/reference/idebugarrayobject2-hasbaseindices.md)|Determina si la matriz tiene índices de base (límites inferiores) definidos.|

## <a name="remarks"></a>Comentarios
 Un evaluador de expresiones utiliza esta interfaz para representar las matrices administradas en un árbol de análisis.

## <a name="requirements"></a>Requisitos
 Encabezado: Ee.h

 Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll