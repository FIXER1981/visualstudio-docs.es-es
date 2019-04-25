---
title: IDiaLoadCallback2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback2 interface
ms.assetid: 9a44277d-cbed-4811-9bad-5a2aa0f09323
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: daf0b48aca06b404824059030052223a8545a6b0
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56641460"
---
# <a name="idialoadcallback2"></a>IDiaLoadCallback2
Recibe las devoluciones de llamada desde el símbolo DIA localizar procedimiento, lo que permite a las restricciones a imponerse en el proceso de localización.

## <a name="syntax"></a>Sintaxis

```
IDiaLoadCallback2 : IDiaLoadCallback
```

## <a name="methods-in-vtable-order"></a>Métodos en orden de Vtable
 Además de los métodos en el [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md) interfaz, esta interfaz expone los métodos siguientes:

|Método|Descripción|
|------------|-----------------|
|[IDiaLoadCallback2::RestrictOriginalPathAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictoriginalpathaccess.md)|Determina si busca un archivo .pdb en el directorio de depuración original.|
|[IDiaLoadCallback2::RestrictReferencePathAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictreferencepathaccess.md)|Determina si se permite la búsqueda de un archivo .pdb en la ruta de acceso donde se encuentra el archivo .exe.|
|[IDiaLoadCallback2::RestrictDBGAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictdbgaccess.md)|Determina si se permite la búsqueda de información de depuración desde archivos .dbg.|
|[IDiaLoadCallback2::RestrictSystemRootAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictsystemrootaccess.md)|Determina si se permite la búsqueda de los archivos .pdb en el directorio raíz del sistema.|

## <a name="remarks"></a>Comentarios
 La aplicación cliente implementa esta interfaz y proporciona una referencia a él en la llamada a la [Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) método. Recuerde que debe implementar todos los métodos en el [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md) interfaz también.

## <a name="requirements"></a>Requisitos
 Encabezado: Dia2.h

 Biblioteca: diaguids.lib

 DLL: msdia80.dll

## <a name="see-also"></a>Vea también
- [Interfaces (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)
- [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)
- [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)
- [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md)