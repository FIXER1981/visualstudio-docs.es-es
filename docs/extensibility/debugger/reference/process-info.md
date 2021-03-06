---
title: PROCESS_INFO | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PROCESS_INFO
helpviewer_keywords:
- PROCESS_INFO structure
ms.assetid: 260c33cc-a05e-4645-84b6-536d0b3b0537
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ef73145fb0a2598dc5e4ee98e8652314e0bc1c89
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80713881"
---
# <a name="process_info"></a>PROCESS_INFO
Contiene información sobre un proceso.

## <a name="syntax"></a>Sintaxis

```cpp
typedef struct tagPROCESS_INFO { 
   PROCESS_INFO_FIELDS Fields;
   BSTR                bstrFileName;
   BSTR                bstrBaseName;
   BSTR                bstrTitle;
   AD_PROCESS_ID       ProcessId;
   DWORD               dwSessionId;
   BSTR                bstrAttachedSessionName;
   FILETIME            CreationTime;
   PROCESS_INFO_FLAGS  Flags;
} PROCESS_INFO;
```

```csharp
public struct PROCESS_INFO { 
   public uint          Fields;
   public string        bstrFileName;
   public string        bstrBaseName;
   public string        bstrTitle;
   public AD_PROCESS_ID ProcessId;
   public uint          dwSessionId;
   public string        bstrAttachedSessionName;
   public FILETIME      CreationTime;
   public uint          Flags;
};
```

## <a name="members"></a>Miembros
 `Fields`\
 Combinación de marcas de la enumeración [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md) que especifican qué campos se rellenan.

 `bstrFileName`\
 Nombre completo de la ruta de acceso del proceso. Equivalente a llamar al método [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md) con el parámetro `GN_FILENAME` .

 `bstrBaseName`\
 El nombre de archivo y la extensión del proceso. Equivalente a llamar al `IDebugProcess2::Getname` método con el parámetro `GN_BASENAME` .

 `bstrTitle`\
 Título del proceso, si existe. Equivalente a llamar al `IDebugProcess2::Getname` método con el parámetro `GN_TITLE` .

 `ProcessId`\
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) estructura que identifica el proceso. Equivalente a llamar al método [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md) .

 `dwSessionId`\
 El identificador de la sesión de depuración en la que se ejecuta este proceso.

 `bstrAttachedSessionName`\
 El nombre de la sesión adjunta. Equivalente a llamar al método [GetAttachedSessionName](../../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md) .

 `CreationTime`\
 La hora a la que se creó el proceso.

 `Flags`\
 Combinación de marcas de la enumeración [PROCESS_INFO_FLAGS](../../../extensibility/debugger/reference/process-info-flags.md) que especifican las propiedades del proceso.

## <a name="remarks"></a>Observaciones
 Esta estructura se pasa al método [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md) en el que se rellena.

## <a name="requirements"></a>Requisitos
 Encabezado: msdbg. h

 Espacio de nombres: Microsoft. VisualStudio. Debugger. Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [Estructuras y uniones](../../../extensibility/debugger/reference/structures-and-unions.md)
- [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md)
- [PROCESS_INFO_FLAGS](../../../extensibility/debugger/reference/process-info-flags.md)
- [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md)
- [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md)
- [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)
- [GetAttachedSessionName](../../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md)
