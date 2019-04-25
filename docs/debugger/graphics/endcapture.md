---
title: EndCapture | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 06084c3b-e065-49b6-968e-d578762fb871
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0ae024f0d91c980fa8e787b21c93d32a6431203e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56695536"
---
# <a name="endcapture"></a>EndCapture
Finaliza un intervalo de captura que se inició con `BeginCapture`.

## <a name="syntax"></a>Sintaxis

```C++
void EndCapture();
```

## <a name="remarks"></a>Comentarios
 Un intervalo de captura suele abarcar un subconjunto de un fotograma, por ejemplo cuando desea capturar información de gráficos solo sobre algún tipo de llamada a Draw. Si el intervalo de captura abarca una llamada de presentación, se capturan dos fotogramas de información de gráficos. El primer fotograma abarca el intervalo entre la llamada a `BeginCapture` y la llamada de presentación; el segundo fotograma abarca el intervalo entre el primer evento de Direct3D después de la llamada de presentación y la llamada a `EndCapture`.

 Para capturar un intervalo, debe preparar la aplicación para capturar y grabar información de gráficos, es decir, debe haber llamado a [Init](init.md) a través de una instancia de la `VsgDbg` antes de llamar a la clase `BeginCapture` o `EndCapture`.

## <a name="see-also"></a>Vea también
- [BeginCapture](begincapture.md)
- [CaptureCurrentFrame](capturecurrentframe.md)