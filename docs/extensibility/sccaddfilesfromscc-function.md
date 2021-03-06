---
title: Función SccAddFilesFromSCC | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccAddFilesFromSCC
helpviewer_keywords:
- SccAddFilesFromSCC function
ms.assetid: f21a3500-ade8-4dd8-8647-10e2179be9c1
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1d22527644edbf1697112f5cf8b73b8a3f72b774
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80701285"
---
# <a name="sccaddfilesfromscc-function"></a>SccAddFilesFromSCC función)
Esta función agrega una lista de archivos del control de código fuente al proyecto actualmente abierto.

## <a name="syntax"></a>Sintaxis

```cpp
SCCRTN SccAddFilesFromSCC(
   LPVOID  pContext,
   HWND    hWnd,
   LPSTR   lpUser,
   LPSTR   lpAuxProjPath,
   LONG    cFiles,
   LPCSTR* lpFilePaths,
   LPCSTR  lpDestination,
   LPCSTR  lpComment,
   LPBOOL  pbResults
);
```

### <a name="parameters"></a>Parámetros
 pContext

de Puntero de contexto del complemento de control de código fuente.

 hWnd

de Identificador de la ventana del IDE que el complemento de control de código fuente puede utilizar como elemento primario para los cuadros de diálogo que proporciona.

 lpUser

[in, out] El nombre de usuario (hasta SCC_USER_SIZE, incluido el terminador nulo).

 lpAuxProjPath

[in, out] Cadena auxiliar que identifica el proyecto (hasta el `SCC_PRJPATH_` tamaño, incluido el terminador nulo).

 cFiles

de Número de archivos especificados por `lpFilePaths` .

 lpFilePaths

[in, out] Matriz de nombres de archivo que se va a agregar al proyecto actual.

 lpDestination

de Ruta de acceso de destino donde se van a escribir los archivos.

 lpComment

de Comentario que se va a aplicar a cada uno de los archivos que se van a agregar.

 pbResults

[in, out] Matriz de marcas que se establecen para indicar que se ha realizado correctamente (distinto de cero o TRUE) o error (cero o FALSE) para cada archivo (el tamaño de la matriz debe ser al menos `cFiles` largo).

## <a name="return-value"></a>Valor devuelto
 Se espera que la implementación del complemento de control de código fuente de esta función devuelva uno de los siguientes valores:

|Value|Descripción|
|-----------|-----------------|
|SCC_E_PROJNOTOPEN|El proyecto no está abierto.|
|SCC_E_OPNOTPERFORMED|La conexión no está en el mismo proyecto que especifica `lpAuxProjPath.`|
|SCC_E_NOTAUTHORIZED|El usuario no está autorizado para actualizar la base de datos.|
|SCC_E_NONSPECIFICERROR|Error desconocido.|
|SCC_I_RELOADFILE|Es necesario volver a cargar un archivo o proyecto.|

## <a name="see-also"></a>Vea también
- [Funciones de la API del complemento de control de código fuente](../extensibility/source-control-plug-in-api-functions.md)
