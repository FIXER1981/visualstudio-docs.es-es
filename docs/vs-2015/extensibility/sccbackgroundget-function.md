---
title: SccBackgroundGet (función) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- SccBackgroundGet
helpviewer_keywords:
- SccBackgroundGet function
ms.assetid: 69817e52-b9ac-4f4d-820b-2cc9c384f0dc
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 118d8458fd9581a87baea08452d0011d4d66c9a1
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "63432486"
---
# <a name="sccbackgroundget-function"></a>SccBackgroundGet (Función)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Esta función recupera de control de código fuente cada de los archivos especificados sin interacción del usuario.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
SCCRTN SccBackgroundGet(  
   LPVOID  pContext,  
   LONG    nFiles,  
   LPCSTR* lpFileNames,  
   LONG    dwFlags,  
   LONG    dwBackgroundOperationID  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 pContext  
 [in] El puntero de contexto de complemento de control de código fuente.  
  
 nFiles  
 [in] Número de archivos especificados en el `lpFileNames` matriz.  
  
 lpFileNames  
 [in, out] Matriz de nombres de archivos que se va a recuperar.  
  
> [!NOTE]
> Los nombres deben ser los nombres de archivo local completa.  
  
 dwFlags  
 [in] Indicadores de comandos (`SCC_GET_ALL`, `SCC_GET_RECURSIVE`).  
  
 dwBackgroundOperationID  
 [in] Un valor único asociado con esta operación.  
  
## <a name="return-value"></a>Valor devuelto  
 La implementación de complemento de control de origen de esta función debe devolver uno de los valores siguientes:  
  
|Valor|Descripción|  
|-----------|-----------------|  
|SCC_OK|Operación se completó correctamente.|  
|SCC_E_BACKGROUNDGETINPROGRESS|Una recuperación en segundo plano ya está en curso (el complemento de control de origen debe devolver esto únicamente si no admite operaciones por lotes simultáneos).|  
|SCC_I_OPERATIONCANCELED|Operación cancelada antes de que se complete.|  
  
## <a name="remarks"></a>Comentarios  
 Esta función siempre se llama en un subproceso diferente del que carga el complemento de control de código fuente. Esta función no debe devolver hasta que se hace; Sin embargo, se puede llamar varias veces con varias listas de archivos, todos al mismo tiempo.  
  
 El uso de la `dwFlags` argumento es el mismo que el [SccGet](../extensibility/sccget-function.md).  
  
## <a name="see-also"></a>Vea también  
 [Funciones de API de complemento de Control de código fuente](../extensibility/source-control-plug-in-api-functions.md)   
 [SccGet](../extensibility/sccget-function.md)
