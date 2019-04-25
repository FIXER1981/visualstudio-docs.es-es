---
title: IDiaEnumSegments | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSegments interface
ms.assetid: 0c9edd5e-b9ce-43e1-a791-cd4c5d16d923
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 255c55dff0dab0c7b36f5029de9e688db949a1fe
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56623572"
---
# <a name="idiaenumsegments"></a>IDiaEnumSegments
Enumera los distintos segmentos contenidos en el origen de datos.

## <a name="syntax"></a>Sintaxis

```
IDiaEnumSegments : IUnknown
```

## <a name="methods-in-vtable-order"></a>Métodos en orden de Vtable
La tabla siguiente muestran los métodos de `IDiaEnumSegments`.

|Método|Descripción|
|------------|-----------------|
|[IDiaEnumSegments::get__NewEnum](../../debugger/debug-interface-access/idiaenumsegments-get-newenum.md)|Recupera el [interfaz IEnumVARIANT](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ienumvariant) versión de este enumerador.|
|[IDiaEnumSegments::get_Count](../../debugger/debug-interface-access/idiaenumsegments-get-count.md)|Recupera el número de segmentos.|
|[IDiaEnumSegments::Item](../../debugger/debug-interface-access/idiaenumsegments-item.md)|Recupera un segmento por medio de un índice.|
|[IDiaEnumSegments::Next](../../debugger/debug-interface-access/idiaenumsegments-next.md)|Recupera un número especificado de segmentos de la secuencia de enumeración.|
|[IDiaEnumSegments::Skip](../../debugger/debug-interface-access/idiaenumsegments-skip.md)|Omite un número especificado de segmentos en una secuencia de enumeración.|
|[IDiaEnumSegments::Reset](../../debugger/debug-interface-access/idiaenumsegments-reset.md)|Restablece una secuencia de enumeración al principio.|
|[IDiaEnumSegments::Clone](../../debugger/debug-interface-access/idiaenumsegments-clone.md)|Crea un enumerador que contiene el mismo estado de enumeración que el enumerador actual.|

## <a name="remarks"></a>Comentarios

## <a name="notes-for-callers"></a>Notas para los llamadores
Esta interfaz se obtiene mediante una llamada a la `QueryInterface` método en un [IDiaTable](../../debugger/debug-interface-access/idiatable.md) objeto. Vea el ejemplo para obtener más información.

## <a name="example"></a>Ejemplo
En este ejemplo se muestra cómo obtener el `IDiaEnumSections` interfaz desde una tabla. Para obtener un ejemplo más completo del uso de segmentos, consulte el [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md) interfaz.

```C++
void ShowSegments(IDiaTable *pTable, IDiaSession *pSession)
{
    CComPtr<IDiaEnumSegments> pSegments;
    if ( SUCCEEDED( pTable->QueryInterface(
                                __uuidof( IDiaEnumSegments ),
                                (void**)&pSegments )
                  )
       )
    {
        // Do something with this enumeration
    }
}
```

## <a name="requirements"></a>Requisitos
Encabezado: Dia2.h

Biblioteca: diaguids.lib

DLL: msdia80.dll

## <a name="see-also"></a>Vea también
- [Interfaces (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaTable](../../debugger/debug-interface-access/idiatable.md)
- [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)
