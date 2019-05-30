---
title: Desactivar las advertencias de compatibilidad para complementos de Control de código fuente | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, turning off compatibility warnings
- compatibility warnings, turning off
ms.assetid: ba318e12-921b-4b7a-a8c2-12c712be1dbf
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6dc8edcb6ee10be8b020424d8f8c247770a98f27
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "66324810"
---
# <a name="how-to-turn-off-compatibility-warnings-for-source-control-plug-ins"></a>Procedimiento Desactivar las advertencias de compatibilidad para complementos de control de código fuente
Un usuario que vea varias advertencias de compatibilidad al emplear el control de código fuente en [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Las advertencias presentarlos dependen de las capacidades del complemento de control de código fuente y se pueden deshabilitar como detallados aquí.

### <a name="to-disable-the-warning-to-ensure-optimal-source-control-integration-with-visual-studio"></a>Para deshabilitar la advertencia: "Para garantizar la integración del control de código fuente óptimo con Visual Studio"

- Establezca la siguiente entrada del registro (agregando el valor si es necesario):

   **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\DontDisplayCheckDotNETCompatible = DWORD: 00000001**

   Esta advertencia se muestra para todos los que no sean de[!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)] los complementos.

### <a name="to-disable-the-warning-the-installed-source-control-provider-does-not-support-all-the-capabilities"></a>Para deshabilitar la advertencia: "El proveedor de control de código fuente instalado no admite todas las capacidades"

- Establezca los siguientes dos valores del registro (agregando los valores si es necesario):

     **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\WarnedOldMSSCCIProvider = dword:00000000**

    **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\UseOldSCC = dword:00000001**

     Esta advertencia se muestra si el complemento de control de código fuente no admita explícitamente la reentrada para varios proyectos (es decir, si puede comprobar en un solo archivo y proyecto a la vez).

     Es mejor admitir la reentrada (`SCC_CAP_REENTRANT` capacidad); al hacerlo eliminará esta advertencia. Sin embargo, si esta compatibilidad no es posible, pueden establecer estas entradas del registro.

## <a name="see-also"></a>Vea también
- [Marcadores de capacidad](../extensibility/capability-flags.md)