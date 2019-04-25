---
title: BP_ERROR_TYPE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_ERROR_TYPE
helpviewer_keywords:
- BP_ERROR_TYPE enumeration
ms.assetid: c483eaab-db29-46de-bfdb-5c2a9a9cfb68
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2964c833abfa25b57678680f8b821f992cb31de8
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689192"
---
# <a name="bperrortype"></a>BP_ERROR_TYPE
Especifica el tipo de error de un punto de interrupción.

## <a name="syntax"></a>Sintaxis

```cpp
enum enum_BP_ERROR_TYPE {
    BPET_NONE            = 0x00000000,
    BPET_TYPE_WARNING    = 0x00000001,
    BPET_TYPE_ERROR      = 0x00000002,
    BPET_SEV_HIGH        = 0x0F000000,
    BPET_SEV_GENERAL     = 0x07000000,
    BPET_SEV_LOW         = 0x01000000,
    BPET_TYPE_MASK       = 0x0000ffff,
    BPET_SEV_MASK        = 0xffff0000,
    BPET_GENERAL_WARNING = BPET_SEV_GENERAL | BPET_TYPE_WARNING,
    BPET_GENERAL_ERROR   = BPET_SEV_GENERAL | BPET_TYPE_ERROR,
    BPET_ALL             = 0xffffffff
};
typedef DWORD BP_ERROR_TYPE;
```

```csharp
public enum enum_BP_ERROR_TYPE {
    BPET_NONE            = 0x00000000,
    BPET_TYPE_WARNING    = 0x00000001,
    BPET_TYPE_ERROR      = 0x00000002,
    BPET_SEV_HIGH        = 0x0F000000,
    BPET_SEV_GENERAL     = 0x07000000,
    BPET_SEV_LOW         = 0x01000000,
    BPET_TYPE_MASK       = 0x0000ffff,
    BPET_SEV_MASK        = 0xffff0000,
    BPET_GENERAL_WARNING = BPET_SEV_GENERAL | BPET_TYPE_WARNING,
    BPET_GENERAL_ERROR   = BPET_SEV_GENERAL | BPET_TYPE_ERROR,
    BPET_ALL             = 0xffffffff
};
```

## <a name="members"></a>Miembros
BPET_NONE se especifica ningún error de punto de interrupción.

BPET_TYPE_WARNING especifica un error de punto de interrupción de advertencia de estilo.

BPET_TYPE_ERROR especifica un error de punto de interrupción de estilo de error.

BPET_SEV_HIGH especifica un error de punto de interrupción de alta gravedad.

BPET_SEV_GENERAL especifica un error de punto de interrupción de gravedad.

BPET_SEV_LOW especifica un error de punto de interrupción de gravedad baja.

BPET_TYPE_MASK especifica un error de punto de interrupción de estilo de máscara.

BPET_SEV_MASK especifica un error de punto de interrupción de estilo de máscara de gravedad.

BPET_GENERAL_WARNING especifica un error de punto de interrupción de estilo de advertencia general.

BPET_GENERAL_ERROR especifica un error de punto de interrupción de estilo de error general.

BPET_ALL especifica todos los tipos de error de punto de interrupción.

## <a name="remarks"></a>Comentarios
Estos valores se pueden combinar con un bit a bit `OR` y se utiliza para la `dwType` miembro de la [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) estructura. Pasado como parámetro a la [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md) método.

Un tipo de error de punto de interrupción se compone de un tipo y un nivel de gravedad. Esto significa que un tipo de error de punto de interrupción nunca es simplemente un tipo (por ejemplo, `BPET_TYPE_ERROR`,) o un nivel de gravedad (por ejemplo, `BPET_SEV_GENERAL`) por sí mismo. `BPET_GENERAL_WARNING` y `BPET_GENERAL_ERROR` proporcionar valores predefinidos para puntos de interrupción de advertencia y error generales.

## <a name="requirements"></a>Requisitos
Encabezado: msdbg.h

Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [Enumeraciones](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)
- [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)
