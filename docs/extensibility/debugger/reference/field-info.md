---
title: FIELD_INFO | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- FIELD_INFO
helpviewer_keywords:
- FIELD_INFO structure
ms.assetid: bfafef6d-0c83-43d7-a779-1f0d24b166a1
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 6e2089746adecc583d04176afca18ad19826ea53
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80736888"
---
# <a name="field_info"></a>FIELD_INFO
Esta estructura describe una variable, un parámetro o un campo local.

## <a name="syntax"></a>Sintaxis

```cpp
typedef struct _tagFieldInfo {
    FIELD_INFO_FIELDS dwFields;
    BSTR              bstrFullName;
    BSTR              bstrName;
    BSTR              bstrType;
    FIELD_MODIFIERS   dwModifiers;
} FIELD_INFO;
```

```csharp
public struct FIELD_INFO {
    public uint   dwFields;
    public string bstrFullName;
    public string bstrName;
    public string bstrType;
    public uint   dwModifiers;
};
```

## <a name="members"></a>Miembros
`dwFields`\
Combinación de marcas de la enumeración [FIELD_INFO_FIELDS](../../../extensibility/debugger/reference/field-info-fields.md) que especifica los miembros que se rellenan.

`bstrFullName`\
Nombre completo del campo.

`bstrName`\
Nombre corto del campo.

`bstrType`\
Tipo del campo.

`dwModifiers`\
Combinación de marcas de la enumeración [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md) que describe el campo.

## <a name="remarks"></a>Observaciones
Esta estructura se pasa al método [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md) en el que se rellena.

## <a name="requirements"></a>Requisitos
Encabezado: SH. h

Espacio de nombres: Microsoft. VisualStudio. Debugger. Interop

Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [Estructuras y uniones](../../../extensibility/debugger/reference/structures-and-unions.md)
- [FIELD_INFO_FIELDS](../../../extensibility/debugger/reference/field-info-fields.md)
- [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md)
- [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)
