---
title: Función SccDirQueryInfo | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- SccDirQueryInfo
helpviewer_keywords:
- SccDirQueryInfo function
ms.assetid: 459e2d99-573d-47c4-b834-6d82c5e14162
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7334ddd1ce6c7f9feac63253246e55b65121e18b
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "90842358"
---
# <a name="sccdirqueryinfo-function"></a>SccDirQueryInfo (Función)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Esta función examina una lista de directorios completos para su estado actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
SCCRTN SccDirQueryInfo(  
LPVOID  pContext,  
LONG    nDirs,  
LPCSTR* lpDirNames,  
LPLONG  lpStatus  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 pContext  
 de Estructura de contexto del complemento de control de código fuente.  
  
 nDirs  
 de El número de directorios seleccionados que se van a consultar.  
  
 lpDirNames  
 de Matriz de rutas de acceso completas de los directorios que se van a consultar.  
  
 lpStatus  
 [in, out] Una estructura de matriz para que el complemento de control de código fuente devuelva las marcas de estado (consulte el [código de estado del directorio](../extensibility/directory-status-code-enumerator.md) para obtener más detalles).  
  
## <a name="return-value"></a>Valor devuelto  
 Se espera que la implementación del complemento de control de código fuente de esta función devuelva uno de los siguientes valores:  
  
|Value|Descripción|  
|-----------|-----------------|  
|SCC_OK|La consulta se realizó correctamente.|  
|SCC_E_OPNOTSUPPORTED|El sistema de control de código fuente no admite esta operación.|  
|SCC_E_ACCESSFAILURE|Hubo un problema al obtener acceso al sistema de control de código fuente, probablemente debido a problemas de red o de contención. Se recomienda un reintento.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Error no específico.|  
  
## <a name="remarks"></a>Notas  
 La función rellena la matriz devuelta con una máscara de bits de bits de la `SCC_DIRSTATUS` familia (vea [código de estado de directorio](../extensibility/directory-status-code-enumerator.md)), una entrada para cada directorio proporcionado. El autor de la llamada asigna la matriz de estado.  
  
 El IDE usa esta función antes de que se cambie el nombre de un directorio para comprobar si el directorio está bajo control de código fuente consultando si tiene un proyecto correspondiente. Si el directorio no está bajo control de código fuente, el IDE puede proporcionar la advertencia adecuada al usuario.  
  
> [!NOTE]
> Si un complemento de control de código fuente decide no implementar uno o más de los valores de estado, los bits no implementados se deben establecer en cero.  
  
## <a name="see-also"></a>Consulte también  
 [Funciones de la API del complemento de control de código fuente](../extensibility/source-control-plug-in-api-functions.md)   
 [Código de estado de directorio](../extensibility/directory-status-code-enumerator.md)
