---
title: PROCESS_INFO | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PROCESS_INFO
helpviewer_keywords:
- PROCESS_INFO structure
ms.assetid: 260c33cc-a05e-4645-84b6-536d0b3b0537
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 3a3418aaa9c2e14454d71d26c0e364ae04244127
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457967"
---
# <a name="processinfo"></a>PROCESS_INFO
Contiene información acerca de un proceso.

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
 Una combinación de marcas de la [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md) enumeración que especifican qué campos se rellenan.

 `bstrFileName`\
 El nombre de ruta de acceso completa del proceso. Equivalente a llamar a la [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md) método con el parámetro `GN_FILENAME`.

 `bstrBaseName`\
 El nombre de archivo y la extensión del proceso. Equivalente a llamar a la `IDebugProcess2::Getname` método con el parámetro `GN_BASENAME`.

 `bstrTitle`\
 El título del proceso, si existe alguno. Equivalente a llamar a la `IDebugProcess2::Getname` método con el parámetro `GN_TITLE`.

 `ProcessId`\
 El [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) estructura que identifica el proceso. Equivalente a llamar a la [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md) método.

 `dwSessionId`\
 El identificador de la sesión de depuración que este proceso se ejecuta en.

 `bstrAttachedSessionName`\
 El nombre de sesión conectado. Equivalente a llamar a la [GetAttachedSessionName](../../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md) método.

 `CreationTime`\
 La hora en que se creó el proceso.

 `Flags`\
 Una combinación de marcas de la [PROCESS_INFO_FLAGS](../../../extensibility/debugger/reference/process-info-flags.md) enumeración que especifican las propiedades del proceso.

## <a name="remarks"></a>Comentarios
 Esta estructura se pasa a la [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md) método donde se rellena.

## <a name="requirements"></a>Requisitos
 Encabezado: msdbg.h

 Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [Estructuras y uniones](../../../extensibility/debugger/reference/structures-and-unions.md)
- [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md)
- [PROCESS_INFO_FLAGS](../../../extensibility/debugger/reference/process-info-flags.md)
- [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md)
- [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md)
- [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)
- [GetAttachedSessionName](../../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md)