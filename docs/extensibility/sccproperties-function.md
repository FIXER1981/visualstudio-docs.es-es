---
title: Función SccProperties | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccProperties
helpviewer_keywords:
- SccProperties function
ms.assetid: 1bed38c9-73d2-4474-9717-f9dc26a89cbe
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bf2dd87efbb50346093144db6e069eea30138e37
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80700505"
---
# <a name="sccproperties-function"></a>SccProperties (Función)
Esta función muestra las propiedades de control de código fuente de un archivo o proyecto.

## <a name="syntax"></a>Sintaxis

```cpp
SCCRTN SccProperties (
   LPVOID pvContext,
   HWND   hWnd,
   LPCSTR lpFileName
);
```

#### <a name="parameters"></a>Parámetros
 pvContext

de Estructura de contexto del complemento de control de código fuente.

 hWnd

de Identificador de la ventana del IDE que el complemento de control de código fuente puede utilizar como elemento primario para los cuadros de diálogo que proporciona.

 lpFileName

de Nombre completo de la ruta de acceso del archivo o proyecto.

## <a name="return-value"></a>Valor devuelto
 Se espera que la implementación del complemento de control de código fuente de esta función devuelva uno de los siguientes valores:

|Value|Descripción|
|-----------|-----------------|
|SCC_OK|Las propiedades se mostraban correctamente.|
|SCC_I_RELOADFILE|El sistema de control de versiones ha modificado las propiedades del archivo, por lo que el IDE debe volver a cargar este archivo.|
|SCC_E_PROJNOTOPEN|El proyecto especificado no se ha abierto en el control de código fuente.|
|SCC_E_NOTAUTHORIZED|El usuario no está autorizado para ver las propiedades de este archivo o proyecto.|
|SCC_E_FILENOTCONTROLLED|El archivo o proyecto especificado no está bajo control de código fuente.|
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Se produjo un error desconocido o general.|

## <a name="remarks"></a>Observaciones
 El complemento de control de código fuente muestra las propiedades en su propio cuadro de diálogo.

 Las propiedades se definen mediante el complemento de control de código fuente y pueden diferir del complemento al complemento. Si el complemento permite al usuario cambiar las propiedades de control de código fuente de un archivo, debe volver `SCC_I_RELOAD` a indicar al IDE que este archivo o proyecto debe recargarse.

## <a name="see-also"></a>Vea también
- [Funciones de API de complemento de control de código fuente](../extensibility/source-control-plug-in-api-functions.md)
