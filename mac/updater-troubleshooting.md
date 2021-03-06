---
title: El actualizador presenta errores al recuperar información
description: Instrucciones sobre cómo recuperarse del error "Error al recuperar la información de actualizaciones". En Visual Studio 2019 para Mac
ms.topic: troubleshooting
author: heiligerdankgesang
ms.author: dominicn
ms.date: 04/13/2019
ms.technology: vs-ide-install
ms.assetid: 31AF914A-C66B-4CD3-9429-39695E0E94AE
ms.openlocfilehash: 2ccef07a2889f66df3e7f217ea292b61ffc0008f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "75405472"
---
# <a name="troubleshooting-updater-has-errors-retrieving-information"></a>Solución del problema: El actualizador presenta errores al recuperar información

En raras ocasiones, puede que vea el mensaje de error "Error al recuperar la información de actualizaciones" al intentar [actualizar Visual Studio para Mac](update.md). Si esto sucede, pruebe los pasos siguientes para corregirlo:

- Compruebe la conexión a Internet. La causa más común de este error es la pérdida de conexión.
  - Si no se puede descargar un componente, puede hacer clic en el botón Reintentar junto a su nombre para intentar de nuevo la descarga.
- Reinicie el IDE.
- Si continúa viendo este mensaje de error, también puede probar a actualizar mediante el instalador si el archivo **.dmg** está todavía en la máquina, o bien puede descargarlo desde [visualstudio.com](https://visualstudio.microsoft.com/vs/mac/).
  - El instalador actualizará todos los componentes instalados en la máquina.
  - Al volver a ejecutar el instalador, también podrá instalar los componentes que falten que no había instalado previamente.
- También puede intentar borrar las descargas en caché mediante la eliminación del archivo ubicado en `~/Library/Caches/VisualStudio/8.0/TempDownload/index.xml`.
- Si está trabajando con una versión anterior de Visual Studio para Mac, es posible que tenga otros números de versión en el directorio `VisualStudio`. Elimine también el archivo `index.xml` de estas rutas de acceso.
