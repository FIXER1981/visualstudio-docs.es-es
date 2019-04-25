---
title: IDebugExtendedField | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugExtendedField interface
ms.assetid: b491499c-af57-47da-87d6-34b7398f6591
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ed0b7300fca935a88b6da9e878d87f5ce443bec9
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56682822"
---
# <a name="idebugextendedfield"></a>IDebugExtendedField
Amplía los tipos de campos que están disponibles para admitir tipos genéricos de código administrado.

## <a name="syntax"></a>Sintaxis

```
IDebugExtendedField : IDebugField
```

## <a name="methods"></a>Métodos
 Además de los métodos en el [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) interfaz, esta interfaz implementa los métodos siguientes:

|Método|Descripción|
|------------|-----------------|
|[GetExtendedKind](../../../extensibility/debugger/reference/idebugextendedfield-getextendedkind.md)|Recupera el tipo de campo extendidas especificado.|
|[IsClosedType](../../../extensibility/debugger/reference/idebugextendedfield-isclosedtype.md)|Determina si el campo representa un tipo cerrado.|

## <a name="requirements"></a>Requisitos
 Encabezado: Sh.h

 Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll