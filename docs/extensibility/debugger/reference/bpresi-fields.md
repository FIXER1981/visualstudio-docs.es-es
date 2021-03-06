---
title: BPRESI_FIELDS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BPRESI_FIELDS
helpviewer_keywords:
- BPRESI_FIELDS enumeration
ms.assetid: 99f17b1e-3e67-4f85-89d6-5c6cf45c8008
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 837bb7d25ab8dea2b146a98cc65d320b58162685
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80737723"
---
# <a name="bpresi_fields"></a>BPRESI_FIELDS
Especifica la información que se va a recuperar sobre la resolución correcta de un punto de interrupción.

## <a name="syntax"></a>Sintaxis

```cpp
enum enum_BPRESI_FIELDS {
    BPRESI_BPRESLOCATION = 0x0001,
    BPRESI_PROGRAM       = 0x0002,
    BPRESI_THREAD        = 0x0004,
    BPRESI_ALLFIELDS     = 0xffffffff
};
typedef DWORD BPRESI_FIELDS;
```

```csharp
public enum enum_BPRESI_FIELDS {
    BPRESI_BPRESLOCATION = 0x0001,
    BPRESI_PROGRAM       = 0x0002,
    BPRESI_THREAD        = 0x0004,
    BPRESI_ALLFIELDS     = 0xffffffff
};
```

## <a name="fields"></a>Campos
`BPRESI_BPRESLOCATION`\
Inicialice/use el `bpResLocation` campo (ubicación de resolución de puntos de interrupción) de la estructura [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) .

`BPRESI_PROGRAM`\
Inicialice o use el `pProgram` campo de la `BP_RESOLUTION_INFO` estructura.

`BPRESI_THREAD`\
Inicialice o use el `pThread` campo de la `BP_RESOLUTION_INFO` estructura.

`BPRESI_ALLFIELDS`\
Especifica todos los campos.

## <a name="remarks"></a>Observaciones
Se pasa al método [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md) para indicar qué campos de la estructura de [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) se van a inicializar.

Estas marcas también se usan para indicar los campos de la `BP_RESOLUTION_INFO` estructura que se usan y son válidos cuando se devuelve esa estructura.

Estos valores se pueden combinar con una operación bit a bit `OR` .

## <a name="requirements"></a>Requisitos
Encabezado: msdbg. h

Espacio de nombres: Microsoft. VisualStudio. Debugger. Interop

Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [Enumeraciones](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)
- [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)
