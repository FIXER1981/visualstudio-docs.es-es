---
title: IDiaStackWalkHelper | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2 interface
ms.assetid: d66e5c84-565d-494e-8486-f91db9a34548
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0143945a266b9c76fefa10e1823a7c3ce01f85e7
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56622376"
---
# <a name="idiastackwalkhelper"></a>IDiaStackWalkHelper
Facilita el recorrido de la pila mediante el archivo de programa depuración (.pdb) de la base de datos.

## <a name="syntax"></a>Sintaxis

```

IDiaStackWalkHelper: IUnknown

```

## <a name="methods-in-vtable-order"></a>Métodos en orden de VTable
 La siguiente tabla muestra los métodos de `IDiaStackWalkHelper`:

|Método|Descripción|
|------------|-----------------|
|[IDiaStackWalkHelper::get_registerValue](../../debugger/debug-interface-access/idiastackwalkhelper-get-registervalue.md)|Recupera el valor de un registro.|
|[IDiaStackWalkHelper::put_registerValue](../../debugger/debug-interface-access/idiastackwalkhelper-put-registervalue.md)|Establece el valor de un registro.|
|[IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md)|Lee un bloque de datos de imagen del archivo ejecutable en la memoria.|
|[IDiaStackWalkHelper::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddress.md)|Busca el marco de pila especificado para la dirección de devolución de función más cercano.|
|[IDiaStackWalkHelper::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddressstart.md)|Busca el marco de pila especificado para una dirección de retorno en o cerca de la dirección de pila especificado.|
|[IDiaStackWalkHelper::frameForVA](../../debugger/debug-interface-access/idiastackwalkhelper-frameforva.md)|Recupera el marco de pila que contiene la dirección virtual especificada.|
|[IDiaStackWalkHelper::symbolForVA](../../debugger/debug-interface-access/idiastackwalkhelper-symbolforva.md)|Recupera el símbolo que contiene la dirección virtual especificada. **Nota:** símbolos deben tener el tipo `SymTagFunctionType` (un valor de la [SymTagEnum (enumeración)](../../debugger/debug-interface-access/symtagenum.md) enumeración).|
|[IDiaStackWalkHelper::pdataForVA](../../debugger/debug-interface-access/idiastackwalkhelper-pdataforva.md)|Devuelve el bloque de datos PDATA asociado con la dirección virtual especificada.|
|[IDiaStackWalkHelper::imageForVA](../../debugger/debug-interface-access/idiastackwalkhelper-imageforva.md)|Recupera la dirección virtual a partir de un archivo ejecutable, dada una dirección virtual en algún lugar en el espacio de memoria del archivo ejecutable.|

## <a name="remarks"></a>Comentarios
 El código DIA para obtener información sobre el archivo ejecutable para construir una lista de marcos de pila durante la ejecución del programa llama a esta interfaz.

## <a name="notes-for-callers"></a>Notas para los llamadores
 Una aplicación cliente implementa esta interfaz para admitir recorrer la pila durante la ejecución del programa. Una instancia de esta interfaz se pasa a la [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md) o [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md) métodos.

## <a name="requirements"></a>Requisitos
 Encabezado: Dia2.h

 Biblioteca: diaguids.lib

 DLL: msdia80.dll

## <a name="see-also"></a>Vea también
- [Interfaces (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
- [Enumeración SymTagEnum](../../debugger/debug-interface-access/symtagenum.md)
- [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)
- [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)