---
title: Procedimiento Instalar a ensamblados de interoperabilidad primarios de Office
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- primary interop assemblies [Office development in Visual Studio], installing
- Office primary interop assemblies, installing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2ddba23ecb6007ff3b678932b118208742d1f0d4
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "60109509"
---
# <a name="how-to-install-office-primary-interop-assemblies"></a>Procedimiento Instalar a ensamblados de interoperabilidad primarios de Office
  Instale los ensamblados de interoperabilidad primarios (PIA) de Microsoft Office al instalar Office.

## <a name="to-install-the-pias-when-you-install-office"></a>Para instalar los PIA al instalar Office

1. Asegúrese de que tiene una versión de .NET Framework que no sea anterior a la 2.0.

2. Instale Microsoft Office y asegúrese de que el **compatibilidad con programación de .NET** característica está activada para las aplicaciones que desea extender (esta característica se incluye en la instalación predeterminada).

    > [!WARNING]
    >  De forma predeterminada, los PIA se incrustan en la solución al compilarla, por lo que no debe distribuir PIA a los usuarios como requisito previo para usar el complemento de VSTO o personalización.

## <a name="see-also"></a>Vea también
- [Ensamblados de interoperabilidad primarios de Office](../vsto/office-primary-interop-assemblies.md)
- [Cómo: Aplicaciones de Office de destino a través de los ensamblados de interoperabilidad primarios](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)
- [Cómo: Configurar un equipo para desarrollar soluciones de Office](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)
- [Cómo: Instalar Visual Studio Tools para Office runtime redistribuible](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md)
- [Información general sobre el desarrollo de soluciones de Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)
- [Introducción a &#40;desarrollo de Office en Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
