---
title: POPLISTFUNC | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- POPDIRLISTFUNC
helpviewer_keywords:
- POPLISTFUNC callback function
ms.assetid: b2199fd5-d707-4628-92dd-e2a01e2f507a
caps.latest.revision: 17
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 8c3ae2ce451f076c33ea5613b71c6d262c1d7a0e
ms.sourcegitcommit: fb8babf5cd72f1fc2f97ffe4ad7b62d91f325f61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2020
ms.locfileid: "90842883"
---
# <a name="poplistfunc"></a>POPLISTFUNC
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

El IDE proporciona esta devolución de llamada al [SccPopulateList](../extensibility/sccpopulatelist-function.md) y la usa el complemento de control de código fuente para actualizar una lista de archivos o directorios (también proporcionados a la `SccPopulateList` función).  
  
 Cuando un usuario elige el comando **Get** en el IDE, el IDE muestra un cuadro de lista de todos los archivos que el usuario puede obtener. Desafortunadamente, el IDE no conoce la lista exacta de todos los archivos que el usuario podría obtener; solo el complemento tiene esta lista. Si otros usuarios han agregado archivos al proyecto de control de código fuente, estos archivos deben aparecer en la lista, pero el IDE no los conoce. El IDE crea una lista de los archivos que considera que el usuario puede obtener. Antes de que muestre esta lista al usuario, llama a [SccPopulateList](../extensibility/sccpopulatelist-function.md) , lo que `,` le permite agregar y eliminar archivos de la lista.  
  
## <a name="signature"></a>Firma  
 El complemento de control de código fuente modifica la lista mediante una llamada a una función implementada por el IDE con el siguiente prototipo:  
  
```cpp#  
typedef BOOL (*POPLISTFUNC) (  
   LPVOID pvCallerData,  
   BOOL fAddRemove,  
   LONG nStatus,  
   LPSTR lpFileName  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 pvCallerData  
 `pvCallerData`Parámetro pasado por el llamador (el IDE) al [SccPopulateList](../extensibility/sccpopulatelist-function.md). El complemento de control de código fuente no debe suponer nada sobre el contenido de este parámetro.  
  
 fAddRemove  
 Si `TRUE` `lpFileName` es, es un archivo que se debe agregar a la lista de archivos. Si `FALSE` `lpFileName` es, es un archivo que se debe eliminar de la lista de archivos.  
  
 nStatus  
 Estado de `lpFileName` (una combinación de `SCC_STATUS` bits; consulte el [código de estado de archivo](../extensibility/file-status-code-enumerator.md) para obtener detalles).  
  
 lpFileName  
 Ruta de acceso completa al directorio del nombre de archivo que se va a agregar o eliminar de la lista.  
  
## <a name="return-value"></a>Valor devuelto  
  
|Value|Descripción|  
|-----------|-----------------|  
|`TRUE`|El complemento puede seguir llamando a esta función.|  
|`FALSE`|Se ha producido un problema en el lado del IDE (por ejemplo, una situación de memoria insuficiente). El complemento debe detener la operación.|  
  
## <a name="remarks"></a>Notas  
 Para cada archivo que el complemento de control de código fuente desea agregar o eliminar de la lista de archivos, llama a esta función, pasando el `lpFileName` . La `fAddRemove` marca indica un nuevo archivo que se va a agregar a la lista o a un archivo anterior que se va a eliminar. El `nStatus` parámetro proporciona el estado del archivo. Cuando el complemento SCC ha terminado de agregar y eliminar archivos, vuelve de la llamada a [SccPopulateList](../extensibility/sccpopulatelist-function.md) .  
  
> [!NOTE]
> El `SCC_CAP_POPULATELIST` bit de capacidad es necesario para Visual Studio.  
  
## <a name="see-also"></a>Consulte también  
 [Funciones de devolución de llamada implementadas por el IDE](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [Complementos de control de código fuente](../extensibility/source-control-plug-ins.md)   
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)   
 [Código de estado de archivo](../extensibility/file-status-code-enumerator.md)
