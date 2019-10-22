---
title: Procedimiento Desactivar las advertencias de compatibilidad para complementos de Control de código fuente | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, turning off compatibility warnings
- compatibility warnings, turning off
ms.assetid: ba318e12-921b-4b7a-a8c2-12c712be1dbf
caps.latest.revision: 22
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a4397b2710a7de4addd97bfcbdb4f8e80e2b9c70
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "68204051"
---
# <a name="how-to-turn-off-compatibility-warnings-for-source-control-plug-ins"></a>Procedimiento Desactivar advertencias de compatibilidad para complementos de control de código fuente
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Un usuario que vea varias advertencias de compatibilidad al emplear el control de código fuente en [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Las advertencias presentarlos dependen de las capacidades del complemento de control de código fuente y se pueden deshabilitar como detallados aquí.  
  
### <a name="to-disable-the-warning-to-ensure-optimal-source-control-integration-with-visual-studio"></a>Para deshabilitar la advertencia: "Para asegurarse de óptima integración del código fuente con Visual Studio..."  
  
- Establezca la siguiente entrada del registro (agregando el valor si es necesario):  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\DontDisplayCheckDotNETCompatible = DWORD: 00000001  
  
     Esta advertencia se muestra para todos los que no sean de[!INCLUDE[vsvss](../includes/vsvss-md.md)] los complementos.  
  
### <a name="to-disable-the-warning-the-installed-source-control-provider-does-not-support-all-the-capabilities"></a>Para deshabilitar la advertencia: "El proveedor de control de código fuente instalado no admite todas las capacidades..."  
  
- Establezca los siguientes dos valores del registro (agregando los valores si es necesario):  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\WarnedOldMSSCCIProvider = dword:00000000  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\UseOldSCC = DWORD: 00000001  
  
     Esta advertencia se muestra si el complemento de control de código fuente no admita explícitamente la reentrada para varios proyectos (es decir, si puede comprobar en un solo archivo y proyecto a la vez).  
  
     Es mejor admitir la reentrada (`SCC_CAP_REENTRANT` capacidad); al hacerlo eliminará esta advertencia. Sin embargo, si esta compatibilidad no es posible, pueden establecer estas entradas del registro.  
  
## <a name="see-also"></a>Vea también  
 [Marcadores de capacidad](../extensibility/capability-flags.md)
