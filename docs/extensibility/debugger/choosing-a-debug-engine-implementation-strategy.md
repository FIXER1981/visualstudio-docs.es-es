---
title: Elegir una estrategia de implementación del motor de depuración | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, implementation strategies
ms.assetid: 90458fdd-2d34-4f10-82dc-6d8f31b66d8b
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 05e66975a2d41108d3d9fb469da9e4a36a10d8d2
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80739126"
---
# <a name="choose-a-debug-engine-implementation-strategy"></a>Elegir una estrategia de implementación del motor de depuración
Use la arquitectura en tiempo de ejecución para determinar la estrategia DE implementación del motor DE depuración (DE). Puede crear el motor de depuración en proceso para el programa que está depurando. Cree el motor de depuración en proceso para el administrador de depuración de sesión (SDM) de Visual Studio. O bien, cree el motor de depuración fuera de proceso en ambos. Las siguientes directrices le ayudarán a elegir entre estas tres estrategias.

## <a name="guidelines"></a>Directrices
 Aunque es posible que el DE sea fuera de proceso para el SDM y el programa que se está depurando, normalmente no hay ninguna razón para hacerlo. Las llamadas a través de los límites del proceso son relativamente lentas.

 Los motores de depuración ya se proporcionan para el entorno de tiempo de ejecución nativo de Win32 y para el entorno en tiempo de ejecución de Common Language Runtime. Si tiene que reemplazar el DE para cualquiera de los entornos, debe crear el de en proceso con el SDM.

 De lo contrario, puede crear el de en proceso para el SDM o en proceso para el programa que está depurando. Tendrá que tener en cuenta si el evaluador de expresiones de requiere acceso frecuente al almacén de símbolos del programa. O bien, si el almacén de símbolos se puede cargar en memoria para un acceso rápido. Además, tenga en cuenta los siguientes enfoques:

- Si no hay muchas llamadas entre el evaluador de expresiones y el almacén de símbolos, o si el almacén de símbolos se puede leer en el espacio de memoria de SDM, cree la de en proceso para el SDM. Debe devolver el CLSID del motor de depuración al SDM cuando se asocia al programa. El SDM usa este CLSID para crear una instancia en proceso de de.

- Si el método DE debe llamar al programa para tener acceso al almacén de símbolos, cree el DE en proceso con el programa. En este caso, el programa crea la instancia de de.

## <a name="see-also"></a>Vea también
- [Extensibilidad del depurador de Visual Studio](../../extensibility/debugger/visual-studio-debugger-extensibility.md)
