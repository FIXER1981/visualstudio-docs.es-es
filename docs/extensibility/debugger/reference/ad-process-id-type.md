---
title: AD_PROCESS_ID_TYPE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AD_PROCESS_ID_TYPE
helpviewer_keywords:
- AD_PROCESS_ID_TYPE enumeration
ms.assetid: 0aab80e9-285a-4697-94ac-c864d42a6aaa
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a9df097037a84af9da63f0a98ee6cfa3b28cfcdd
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "66351390"
---
# <a name="adprocessidtype"></a>AD_PROCESS_ID_TYPE
Especifica cómo interpretar un identificador de proceso en el [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) estructura.

## <a name="syntax"></a>Sintaxis

```cpp
enum enum_AD_PROCESS_ID {
    AD_PROCESS_ID_SYSTEM = 0,
    AD_PROCESS_ID_GUID   = 1
};
typedef DWORD AD_PROCESS_ID_TYPE;
```

```csharp
public enum enum_AD_PROCESS_ID {
    AD_PROCESS_ID_SYSTEM = 0,
    AD_PROCESS_ID_GUID   = 1
};
```

## <a name="fields"></a>Campos
`AD_PROCESS_ID_SYSTEM`\
Id. de proceso es un identificador de sistema. Use la `ProcessId.dwProcessId` campo de la [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) estructura.

`AD_PROCESS_ID_GUID`\
Id. de proceso es un GUID. Use la `ProcessId.guidProcessId` campo de la `AD_PROCESS_ID` estructura.

## <a name="remarks"></a>Comentarios
Utilizado para la `ProcessIdType` miembro de la [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) estructura para identificar el tipo de identificador de proceso que se encuentra en la estructura. Determina cómo se interpretan los `ProcessId` union en la estructura.

## <a name="requirements"></a>Requisitos
Encabezado: msdbg.h

Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [Enumeraciones](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)
