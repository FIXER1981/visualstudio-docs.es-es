---
title: SccGetUserOption (función) | Documentos de Microsoft
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccGetUserOption
helpviewer_keywords:
- SccGetUserOption function
ms.assetid: 17863747-1901-4c53-a2b3-ed996085e120
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8b237ded8ac0d22500986a9d390834147f24a2c6
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56721272"
---
# <a name="sccgetuseroption-function"></a>SccGetUserOption (Función)
Esta función recupera una variedad de opciones específicas del usuario.

## <a name="syntax"></a>Sintaxis

```cpp
SCCRTN SccGetUserOption(
   LPVOID pContext,
   LONG nOption,
   LPLONG lpVal
);
```

#### <a name="parameters"></a>Parámetros
 pContext

[in] El puntero de contexto de complemento de control de código fuente.

 nOption

[in] Opción para recuperar (vea la sección Comentarios para las opciones posibles).

 lpVal

[out] Valor asociado con la opción.

## <a name="return-value"></a>Valor devuelto
 La implementación de complemento de control de origen de esta función debe devolver uno de los valores siguientes:

|Valor|Descripción|
|-----------|-----------------|
|SCC_OK|Opción se recuperó correctamente.|
|SCC_E_OPNOTSUPPORTED|No se admite la opción.|
|SCC_E_NONSPECIFICERROR|Se ha producido un error no especificado.|

## <a name="remarks"></a>Comentarios
 Este comando admite las siguientes opciones:

|Opción de usuario|Descripción|
|-----------------|-----------------|
|`SCC_USEROPT_CHECKOUT_LOCALVER`|Determina si el usuario desea desproteger versión local de archivos. `lpVal` se asigna `SCC_USEROPT_COLV_YES` (usuario desea desproteger los archivos locales) o `SCC_USEROPT_COLV_NO`.|

## <a name="see-also"></a>Vea también
- [Funciones de API de complemento de control de código fuente](../extensibility/source-control-plug-in-api-functions.md)
- [Códigos de error](../extensibility/error-codes.md)