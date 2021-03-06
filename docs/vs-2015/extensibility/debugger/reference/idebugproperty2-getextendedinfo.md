---
title: 'IDebugProperty2:: GetExtendedInfo | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProperty2::GetExtendedInfo
helpviewer_keywords:
- IDebugProperty2::GetExtendedInfo
ms.assetid: 0c9c0b2b-7540-4424-adb5-fce7aa37a026
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 74810aab2f47a36c716891fd45b7424eb737b142
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68164974"
---
# <a name="idebugproperty2getextendedinfo"></a>IDebugProperty2::GetExtendedInfo
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Obtiene información extendida para la propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
HRESULT GetExtendedInfo (   
   REFGUID* guidExtendedInfo,  
   VARIANT* pExtendedInfo  
);  
```  
  
```csharp  
int GetExtendedInfo (   
   ref Guid guidExtendedInfo,  
   out object pExtendedInfo  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `guidExtendedInfo`  
 de GUID que determina el tipo de información extendida que se va a recuperar. Para obtener información detallada, vea la sección Comentarios de.  
  
 `pExtendedInfo`  
 enuncia Devuelve un `VARIANT` (C++) o un objeto (C#) que se puede utilizar para recuperar la información de la propiedad extendida. Por ejemplo, este parámetro puede devolver una `IUnknown` interfaz que se puede consultar para una interfaz [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md) . Para obtener información detallada, vea la sección Comentarios de.  
  
## <a name="return-value"></a>Valor devuelto  
 Si es correcto, devuelve `S_OK` ; de lo contrario, devuelve el código de error. Devuelve `S_GETEXTENDEDINFO_NO_EXTENDEDINFO` si no hay información extendida para recuperar.  
  
## <a name="remarks"></a>Comentarios  
 Este método existe con el fin de recuperar información que no se presta para recuperarse llamando al método [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) .  
  
 Los siguientes GUID se reconocen normalmente por este método (los valores GUID se especifican para C#, ya que el nombre no está disponible en ningún ensamblado). Se pueden crear GUID adicionales para uso interno.  
  
|Nombre|GUID|Descripción|  
|----------|----------|-----------------|  
|guidDocument|{3f98de84-fee9-11d0-b47f-00a0244a1dd2}|Devuelve una `IUnknown` interfaz al documento. Normalmente, la interfaz [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md) se puede obtener desde esta `IUnknown` interfaz.|  
|guidCodeContext|{e2fc65e-56ce-11d1-b528-00aax004a8797}|Devuelve una `IUnknown` interfaz al contexto del documento. Normalmente, la interfaz [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) se puede obtener desde esta `IUnknown` interfaz.|  
|guidCustomViewerSupported|{d9c9da31-ffbe-4eeb-9186-23121e3c088c}|Devuelve una cadena que contiene el CLSID de un visor personalizado, implementado normalmente por un evaluador de expresiones.|  
|guidExtendedInfoSlot|{6df235ad-82c6-4292-9c97-7389770bc42f}|Devuelve un número de 32 bits que representa el número de ranura deseado si esta propiedad representa una dirección local de código administrado.|  
|guidExtendedInfoSignature|{b5fb6d46-f805-417f-96a3-8ba737073ffd}|Devuelve una cadena que contiene la firma de la variable asociada al objeto de propiedad.|  
  
## <a name="see-also"></a>Consulte también  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)
