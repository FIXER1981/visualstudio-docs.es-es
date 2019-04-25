---
title: Servicios proporcionados (VSPackage de Control de código fuente) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- services, source control packages
- source control packages, services
ms.assetid: 9db07d70-87d2-4401-bc88-e3a49d81e9a2
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4f9a4a873f2b6b3f41bd86d046bc187c17f063f1
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56601158"
---
# <a name="services-provided-source-control-vspackage"></a>Servicios proporcionados (VSPackage de control de código fuente)
Los servicios son el mecanismo principal a través del cual la funcionalidad se comparte entre VSPackages y entre el entorno de desarrollo integrado (IDE) de Visual Studio y su VSPackages instalados. Para una descripción detallada de los servicios y su importancia en el IDE de Visual Studio, consulte[Using y proporcionar servicios](../../extensibility/using-and-providing-services.md).

## <a name="the-source-control-service"></a>El servicio de Control de código fuente
 Visual Studio proporciona dos capas de servicios, servicios de nivel de IDE y servicios de nivel de paquete. El IDE de Visual Studio proporciona servicios de nivel de IDE de forma nativa. El paquete de control de código fuente consume algunos de estos servicios. El paquete de control de código fuente como un paquete VSPackage comparte su funcionalidad de control de código fuente, ya que proporciona un servicio de control de origen privada propia. El paquete de control de código fuente encapsula el conjunto de interfaces relacionadas con el control de origen implementados por el objeto en forma de un contrato que se puede utilizar el IDE de Visual Studio.

## <a name="see-also"></a>Vea también
- [Elementos de diseño](../../extensibility/internals/source-control-vspackage-design-elements.md)