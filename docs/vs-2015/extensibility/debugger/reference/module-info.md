---
title: MODULE_INFO | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- MODULE_INFO
helpviewer_keywords:
- MODULE_INFO structure
ms.assetid: f2e06180-1ab3-4eb5-a428-7994cceb61b6
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 04a8756fd7eb2a4b938ebcd2d5f4754509b704e3
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68205220"
---
# <a name="module_info"></a>MODULE_INFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Describe un módulo determinado (DLL, EXE o Assembly).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
typedef struct tagMODULE_INFO {   
   MODULE_INFO_FIELDS dwValidFields;  
   BSTR               m_bstrName;  
   BSTR               m_bstrUrl;  
   BSTR               m_bstrVersion;  
   BSTR               m_bstrDebugMessage;  
   UINT64             m_addrLoadAddress;  
   UINT64             m_addrPreferredLoadAddress;  
   DWORD              m_dwSize;  
   DWORD              m_dwLoadOrder;  
   FILETIME           m_TimeStamp;  
   BSTR               m_bstrUrlSymbolLocation;  
   MODULE_FLAGS       m_dwModuleFlags;  
} MODULE_INFO;  
```  
  
```csharp  
public struct MODULE_INFO {   
   public uint     dwValidFields;  
   public string   m_bstrName;  
   public string   m_bstrUrl;  
   public string   m_bstrVersion;  
   public string   m_bstrDebugMessage;  
   public ulong    m_addrLoadAddress;  
   public ulong    m_addrPreferredLoadAddress;  
   public uint     m_dwSize;  
   public uint     m_dwLoadOrder;  
   public FILETIME m_TimeStamp;  
   public string   m_bstrUrlSymbolLocation;  
   public uint     m_dwModuleFlags;  
};  
```  
  
## <a name="members"></a>Miembros  
 dwValidFields  
 Combinación de marcas de la enumeración [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md) que especifica qué campos se rellenan.  
  
 m_bstrName  
 Nombre del módulo.  
  
 m_bstrUrl  
 Dirección URL del módulo.  
  
 m_bstrVersion  
 Versión del módulo.  
  
 m_bstrDebugMessage  
 Un mensaje opcional sobre el módulo, por ejemplo, "no se pueden cargar los símbolos".  
  
 m_addrLoadAddress  
 Dirección de carga del módulo.  
  
 m_addrPreferredLoadAddress  
 Dirección de carga preferida del módulo.  
  
 m_dwSize  
 Tamaño del módulo.  
  
 m_dwLoadOrder  
 El orden de carga del módulo.  
  
 m_TimeStamp  
 La hora en que se modificó por última vez el archivo de símbolos.  
  
 m_bstrUrlSymbolLocation  
 Ubicación del archivo de símbolos (por ejemplo, ". \\ ") especificada en el módulo. Se usa como ubicación inicial para buscar símbolos para un módulo.  
  
 m_dwModuleFlags  
 Combinación de marcas de la enumeración [MODULE_FLAGS](../../../extensibility/debugger/reference/module-flags.md) que describe el módulo.  
  
## <a name="remarks"></a>Observaciones  
 Esta estructura se pasa al método [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md) en el que se rellena.  
  
 Esta estructura corresponde a cada módulo que se muestra en la ventana **módulos** .  
  
## <a name="requirements"></a>Requisitos  
 Encabezado: msdbg. h  
  
 Espacio de nombres: Microsoft. VisualStudio. Debugger. Interop  
  
 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Consulte también  
 [Estructuras y uniones](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)   
 [MODULE_FLAGS](../../../extensibility/debugger/reference/module-flags.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)
