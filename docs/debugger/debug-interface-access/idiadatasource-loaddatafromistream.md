---
title: IDiaDataSource::loadDataFromIStream | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::loadDataFromIStream method
ms.assetid: 8fe33eea-1457-4b8c-ae19-f1ede5578483
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cb9b218935085b04ae1a9931733aeca34766aa5f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56641954"
---
# <a name="idiadatasourceloaddatafromistream"></a>IDiaDataSource::loadDataFromIStream
Prepara los datos de depuración almacenados en el archivo de programa (.pdb) de la base de datos tiene acceso a través de un flujo de datos en memoria.

## <a name="syntax"></a>Sintaxis

```C++
HRESULT loadDataFromIStream ( 
   IStream* pIStream
);
```

#### <a name="parameters"></a>Parámetros
 pIStream

[in] Un <xref:IStream> objeto que representa el flujo de datos para usar.

## <a name="return-value"></a>Valor devuelto
 Si es correcto, devuelve `S_OK`; en caso contrario, devuelve un código de error. En la tabla siguiente se muestra los posibles valores devueltos para este método.

|Valor|Descripción|
|-----------|-----------------|
|E_PDB_FORMAT|Se ha intentado obtener acceso a un archivo con un formato obsoleto.|
|E_INVALIDARG|Parámetro no válido.|
|E_UNEXPECTED|Ya se ha preparado el origen de datos.|

## <a name="remarks"></a>Comentarios
 Este método permite a los datos de depuración para que pueda obtenerse a partir de la memoria a través de un ejecutable una <xref:IStream> objeto.

 Para cargar un archivo .pdb sin validación, utilice la [Loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) método.

 Para validar el archivo .pdb en criterios específicos, use el [Loadandvalidatedatafrompdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md) método.

 Para obtener acceso al proceso de carga de datos (a través de un mecanismo de devolución de llamada), utilice el [Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) método.

## <a name="see-also"></a>Vea también
- [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)
- [IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)
- [IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)