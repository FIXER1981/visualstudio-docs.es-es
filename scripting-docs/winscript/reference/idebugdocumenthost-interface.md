---
title: IDebugDocumentHost (interfaz) | Documentos de Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentHost interface
ms.assetid: 2fed4220-b6a2-47c6-bf28-daad7dd5c42d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 226e2700b471cd34496682d233e57946e124ff3b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62939232"
---
# <a name="idebugdocumenthost-interface"></a>IDebugDocumentHost (Interfaz)
Expone la funcionalidad específica del host, como el color de sintaxis, el depurador. El `IDebugDocumentHelper::SetDebugDocumentHost` método toma esta interfaz como un argumento.  
  
 Además de los métodos heredados de `IUnknown`, el `IDebugDocumentHost` interfaz expone los métodos siguientes.  
  
## <a name="methods-in-vtable-order"></a>Métodos en orden de Vtable  
  
|Método|Descripción|  
|------------|-----------------|  
|[IDebugDocumentHost::GetDeferredText](../../winscript/reference/idebugdocumenthost-getdeferredtext.md)|Devuelve un rango de caracteres que se han agregado mediante `IDebugDocumentHelper::AddDeferredText`, en el documento de host original.|  
|[IDebugDocumentHost::GetScriptTextAttributes](../../winscript/reference/idebugdocumenthost-getscripttextattributes.md)|Devuelve los atributos de texto de un bloque de texto del documento.|  
|[IDebugDocumentHost::OnCreateDocumentContext](../../winscript/reference/idebugdocumenthost-oncreatedocumentcontext.md)|Notifica al host que se va a crear un nuevo contexto de documento y permite al host también pueden devolver un objeto que controla el nuevo contexto.|  
|[IDebugDocumentHost::GetPathName](../../winscript/reference/idebugdocumenthost-getpathname.md)|Devuelve la ruta de acceso completa (incluido el nombre de archivo) del archivo de origen del documento.|  
|[IDebugDocumentHost::GetFileName](../../winscript/reference/idebugdocumenthost-getfilename.md)|Devuelve el nombre del documento, sin información de ruta de acceso.|  
|[IDebugDocumentHost::NotifyChanged](../../winscript/reference/idebugdocumenthost-notifychanged.md)|Notifica al host que se ha guardado el archivo de código fuente del documento y que se debe actualizar su contenido.|