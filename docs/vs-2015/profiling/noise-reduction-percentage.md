---
title: Porcentaje de reducción de ruido | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.filter
helpviewer_keywords:
- Concurrency Visualizer, Noise Reduction Percentage
ms.assetid: 1c10cd4c-2fdd-48c9-b562-a334b3b2df6c
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c6407b40f58c3acc02705379768085793a2b79b6
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54787714"
---
# <a name="noise-reduction-percentage"></a>Porcentaje de reducción de ruido
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

De forma predeterminada, el valor del porcentaje de reducción de ruido es 2. Solo las entradas que tienen un porcentaje de tiempo inclusivo mayor o igual que esta configuración se muestran en el árbol de llamadas. Si cambia el valor, puede controlar el número de entradas que se muestran en el árbol de llamadas. Por ejemplo, cambiar el valor a 10 mostrará solo entradas del árbol de llamadas que tienen un tiempo inclusivo mayor o igual al 10 %. Al aumentar la configuración, puede centrarse en las entradas que tienen un impacto mayor en el rendimiento del proceso.
