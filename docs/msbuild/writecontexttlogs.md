---
title: WriteContextTLogs | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- WriteContextTLogs
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- WriteContextTLogs
ms.assetid: ffc6c7be-3f22-4624-9ffc-0122fe72b6ec
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 722d8c42786a7aaa2daae293b96f7926abcc90ca
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62777849"
---
# <a name="writecontexttlogs"></a>WriteContextTLogs
Escribe archivos de registro para el contexto actual.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT WINAPI WriteContextTLogs(LPCTSTR intermediateDirectory, LPCTSTR tlogRootName);
```

#### <a name="parameters"></a>Parámetros
[in] `intermediateDirectory`

 El directorio en el que almacenar el registro de seguimiento.

[in] `tlogRootName`

 El nombre raíz del nombre del archivo de registro.

## <a name="return-value"></a>Valor devuelto
 Un elemento **HRESULT** con el conjunto de bits **SUCCEEDED** si el contexto de seguimiento se ha creado.

## <a name="requirements"></a>Requisitos
 **Encabezado**: *FileTracker.h*

## <a name="see-also"></a>Vea también
- [WriteAllTLogs](../msbuild/writealltlogs.md)