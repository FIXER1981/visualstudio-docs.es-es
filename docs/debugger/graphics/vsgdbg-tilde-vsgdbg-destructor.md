---
title: VsgDbg::~VsgDbg (Destructor) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7a3b97fb-d344-4df7-b195-9347d1edfcf7
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 64d2ce58a0a543a6bccfca4d96ff57915d45ce49
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686566"
---
# <a name="vsgdbgvsgdbg-destructor"></a>VsgDbg::~VsgDbg (Destructor)
Destruye una instancia de la clase `VsgDbg`. Si se está grabando activamente información de gráficos, el archivo de registro de gráficos se finaliza y se cierra, y se liberan los recursos utilizados mientras se capturaba activamente información de gráficos.

## <a name="syntax"></a>Sintaxis

```C++
~VsgDbg();
```

## <a name="see-also"></a>Vea también
- [VsgDbg::VsgDbg (Constructor)](vsgdbg-vsgdbg-constructor.md)