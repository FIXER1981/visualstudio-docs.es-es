---
title: IActiveScriptError | Documentos de Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptError interface
ms.assetid: c8e0288d-38ff-4145-a7e3-f8cdfb72eefe
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1ca783e2100fe74ed05499f9611a9b8f3399817f
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "58144425"
---
# <a name="iactivescripterror"></a>IActiveScriptError
Un objeto que implementa esta interfaz se pasa a la [IActiveScriptSite::OnScriptError](../../winscript/reference/iactivescriptsite-onscripterror.md) método siempre que el motor de scripting encuentra un error no controlado. El host, a continuación, llama a métodos en este objeto para obtener información sobre el error que se ha producido.  
  
## <a name="methods-in-vtable-order"></a>Métodos en orden de Vtable  
  
|Método|Descripción|  
|------------|-----------------|  
|[IActiveScriptError::GetExceptionInfo](../../winscript/reference/iactivescripterror-getexceptioninfo.md)|Recupera información sobre un error.|  
|[IActiveScriptError::GetSourcePosition](../../winscript/reference/iactivescripterror-getsourceposition.md)|Recupera la ubicación en el código fuente donde se produjo un error.|  
|[IActiveScriptError::GetSourceLineText](../../winscript/reference/iactivescripterror-getsourcelinetext.md)|Recupera la línea en el archivo de origen donde se produjo un error.|  
  
## <a name="see-also"></a>Vea también  
 [Active Script (Interfaces)](../../winscript/reference/active-script-interfaces.md)