---
title: OPTNAMECHANGEPFN | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- OPTNAMECHANGEPFN
helpviewer_keywords:
- OPTNAMECHANGEPFN callback function
ms.assetid: 147303f3-c7f1-438a-81b7-db891ea3d076
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4969dff811b6517c0274a35884703a9dc0c693cb
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68194106"
---
# <a name="optnamechangepfn"></a>OPTNAMECHANGEPFN
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Se trata de una función de devolución de llamada especificada en una llamada a [SccSetOption](../extensibility/sccsetoption-function.md) (mediante la opción `SCC_OPT_NAMECHANGEPFN` ) y se utiliza para comunicar los cambios de nombre realizados por el complemento de control de código fuente al IDE.  
  
## <a name="signature"></a>Firma  
  
```cpp#  
typedef void (*OPTNAMECHANGEPFN)(  
   LPVOID pvCallerData,  
   LPCSTR pszOldName,  
   LPCSTR pszNewName  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 pvCallerData  
 de Valor de usuario especificado en una llamada anterior a [SccSetOption](../extensibility/sccsetoption-function.md) (con la opción `SCC_OPT_USERDATA` ).  
  
 pszOldName  
 de Nombre original del archivo.  
  
 pszNewName  
 de Nombre al que se ha cambiado el nombre del archivo.  
  
## <a name="return-value"></a>Valor devuelto  
 Ninguno.  
  
## <a name="remarks"></a>Comentarios  
 Si se cambia el nombre de un archivo durante una operación de control de código fuente, el complemento de control de código fuente puede notificar al IDE sobre el cambio de nombre a través de esta devolución de llamada.  
  
 Si el IDE no admite esta devolución de llamada, no llamará a [SccSetOption](../extensibility/sccsetoption-function.md) para especificarla. Si el complemento no admite esta devolución de llamada, se devolverá `SCC_E_OPNOTSUPPORTED` de la `SccSetOption` función cuando el IDE intente establecer la devolución de llamada.  
  
## <a name="see-also"></a>Consulte también  
 [Funciones de devolución de llamada implementadas por el IDE](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccSetOption](../extensibility/sccsetoption-function.md)
