---
title: No se puede ir automáticamente al servidor | Microsoft Docs
ms.date: 11/04/2016
ms.topic: error-reference
f1_keywords:
- vs.debug.error.causality_no_server_response
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, notification error
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 60c7fac588985c692cd3e432235637e3f82ee852
ms.sourcegitcommit: 062615c058d2ff44751e8d0c704ccfa3c5543469
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90852685"
---
# <a name="error-unable-to-automatically-step-into-the-server"></a>Error: No se puede depurar paso a paso por instrucciones el servidor automáticamente
El error reza como sigue:

 No se puede ir al servidor automáticamente. El depurador no recibió una notificación antes de que se ejecutase el procedimiento remoto

 Este error puede aparecer cuando intenta ir a un servicio Web (vea [Ejecutar paso a paso un servicio Web XML](/previous-versions/zc57803s(v=vs.100))). Puede producirse cuando [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] no se configura correctamente.

 Las posibles causas son:

- No se ha establecido la depuración en "true" en el archivo web.config de la aplicación [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] (vea [Modo de depuración en aplicaciones ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)).

- Se instaló una versión de [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] después de instalar Visual Studio. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] debe instalarse antes que Visual Studio. En Windows, seleccione **Panel de control > Programas y características** para reparar su instalación de Visual Studio.

## <a name="see-also"></a>Vea también
- [Errores de la depuración remota y sus soluciones](../debugger/remote-debugging-errors-and-troubleshooting.md)
- [Remote Debugging](../debugger/remote-debugging.md)