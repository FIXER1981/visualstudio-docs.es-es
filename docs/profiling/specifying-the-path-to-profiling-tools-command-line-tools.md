---
title: Especificación de la ruta de acceso a las herramientas de línea de comandos de generación de perfiles
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7047bf18-5779-4f6e-872c-66e2fc47c969
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: fb445e23b5d507bafb7fece40bf606bbfb76c370
ms.sourcegitcommit: 566144d59c376474c09bbb55164c01d70f4b621c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2020
ms.locfileid: "90809190"
---
# <a name="specify-the-path-to-profiling-tools-command-line-tools"></a>Especificar la ruta de acceso a las herramientas de línea de comandos de las Herramientas de generación de perfiles

La ruta de acceso a las herramientas de línea de comandos de las herramientas de generación de perfiles de [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] no se agrega a la variable de entorno PATH. En equipos de 32 bits, las herramientas se encuentran en un único directorio. En los equipos de 64 bits, están disponibles las versiones de 32 y 64 bits de las herramientas de generación de perfiles.

## <a name="32-bit-computers"></a>Equipos de 32 bits

Para el código nativo, las API del generador de perfiles de Visual Studio se encuentran en *VSPerf.dll*. El archivo de encabezado (*VSPerf.h*) y la biblioteca de importación (*VSPerf.lib*) se encuentran en el directorio *Microsoft Visual Studio\2017\Team Tools\Performance Tools\PerfSDK*.

 Para el código administrado, las API del generador de perfiles se encuentran en *Microsoft.VisualStudio.Profiler.dll*. Este archivo DLL se encuentra en el directorio *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools*.

## <a name="64-bit-computers"></a>Equipos de 64 bits

En los equipos de 64 bits, especifique la ruta de acceso según la plataforma de destino de la aplicación para la que se genera el perfil.

- En las aplicaciones de 32 bits, el directorio de herramientas de generador de perfiles predeterminado es:

     (nativo) *Microsoft Visual Studio\2017\Team Tools\Performance Tools\PerfSDK*
     
     (administrado) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools*

- En las aplicaciones de 64 bits, el directorio de herramientas de generador de perfiles predeterminado es:

     (nativo) *Microsoft Visual Studio\2017\Team Tools\Performance Tools\x64\PerfSDK*

     (administrado) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools\x64*
