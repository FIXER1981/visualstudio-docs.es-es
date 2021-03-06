---
title: Registrar VSPackages | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- managed VSPackages, registering
- registration, managed VSPackages
ms.assetid: 79b9424e-7e9b-4fc8-9b9f-00212674573c
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b40793a5ab317b6a467e55df13302f19cec82640
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80705744"
---
# <a name="registering-vspackages"></a>Registro de VSPackages
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] se basa en los archivos. pkgdef para describir y buscar un VSPackage. Un archivo. pkgdef contiene toda la información de registro que, de lo contrario, se agregaría al registro del sistema. Los VSPackages administrados se registran agregando atributos al código fuente y, a continuación, ejecutando la [utilidad CreatePkgDef](../../extensibility/internals/createpkgdef-utility.md) en el ensamblado resultante para generar un archivo. pkgdef.

## <a name="in-this-section"></a>En esta sección
- [Especificación de la ubicación del archivo de VSPackage en el Shell de VS](../../extensibility/internals/specifying-vspackage-file-location-to-the-vs-shell.md)

 Describe la ruta de acceso de carga para VSPackages.

- [Registrar y anulación deel registro de VSPackages](../../extensibility/registering-and-unregistering-vspackages.md)

 Explica cómo registrar un VSPackage.
