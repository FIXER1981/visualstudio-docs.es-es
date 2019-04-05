---
title: Filtrar Depurar excepciones de ASP.NET | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], ASP.NET exceptions
- ASP.NET, exceptions
- exceptions, ASP.NET
ms.assetid: 1810096e-de8c-435e-be3d-f365d0cd0a6a
caps.latest.revision: 26
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c34ac4fdcf50d1fde95c957de6aff4b7f004a2d3
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "58997328"
---
# <a name="how-to-debug-aspnet-exceptions"></a>Filtrar Depuración de excepciones de ASP.NET
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La depuración de excepciones es una parte importante del desarrollo de una aplicación [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] sólida. Información general sobre cómo depurar excepciones es en [administrar excepciones con el depurador](../debugger/managing-exceptions-with-the-debugger.md).  
  
 Para depurar excepciones no controladas de [!INCLUDE[vstecasp](../includes/vstecasp-md.md)], debe asegurarse de que el depurador se detenga en ellas. El runtime de [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] tiene un controlador de excepciones de nivel superior. Por consiguiente, el depurador nunca se interrumpe en excepciones no controladas de forma predeterminada. Para interrumpir el depurador cuando se produce una excepción, debe seleccionar **interrumpir cuando una excepción es: Produce** para esa excepción específica en el **excepciones** cuadro de diálogo.  
  
 Si ha habilitado sólo mi código, **interrumpir cuando una excepción es: Produce** no hace que el depurador se interrumpa inmediatamente si se produce una excepción en un método de .NET Framework u otro código del sistema. En su lugar, la ejecución continúa hasta que el depurador llega a código que no es del sistema y, a continuación, se interrumpe. Como resultado, no tiene que recorrer el código del sistema cuando se produce una excepción.  
  
 Solo mi código le ofrece otra opción que puede ser aun más útil: **Interrumpir cuando una excepción es: User-unhandled**. Si elige esta configuración para una excepción, el depurador interrumpirá la ejecución en el código de usuario, pero solo si el código de usuario no detecta y controla la excepción. Esta configuración anula el efecto del controlador de excepciones [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] de nivel superior, puesto que se encuentra en código que no es de usuario.  
  
### <a name="to-enable-debugging-of-aspnet-exceptions-with-just-my-code"></a>Para habilitar la depuración de las excepciones ASP.NET con Sólo mi código  
  
1.  En el menú **Depurar**, haga clic en **Excepciones**.  
  
     Aparecerá el cuadro de diálogo **Excepciones**.  
  
2.  Seleccione **Producida** o **No controlada por el usuario**, en la fila **Excepciones de Common Language Runtime**.  
  
     Para utilizar la configuración **No controlada por el usuario**, debe habilitar **Solo mi código**.  
  
### <a name="to-use-best-practices-for-aspnet-exception-handling"></a>Para llevar a cabo los procedimientos recomendados para el control de excepciones ASP.NET  
  
-   Sitúe los bloques `try … catch` alrededor del código susceptible de producir excepciones que pueda prever y sepa cómo controlar. Por ejemplo, si la aplicación realiza llamadas a un servicio Web XML o directamente a un servidor SQL Server, que el código debe estar en **try... catch** bloquea porque hay numerosas excepciones que pueden producirse.
