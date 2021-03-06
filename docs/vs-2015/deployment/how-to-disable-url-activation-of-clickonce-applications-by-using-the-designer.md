---
title: 'Cómo: deshabilitar la activación de direcciones URL de aplicaciones ClickOnce mediante el diseñador | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- disallowURLActivation
- URL activation, ClickOnce applications
- ClickOnce deployment, URL activation
ms.assetid: a337a582-e67c-409a-b52e-607cd1a8fc57
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 27690ab275d0c7ef2a090fa8ef2e42887ae9daeb
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68153810"
---
# <a name="how-to-disable-url-activation-of-clickonce-applications-by-using-the-designer"></a>Cómo: Deshabilitar la activación de direcciones URL de aplicaciones ClickOnce mediante el diseñador
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Normalmente, una [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplicación se iniciará automáticamente inmediatamente después de instalarla desde un servidor Web. Por motivos de seguridad, puede decidir deshabilitar este comportamiento e indicar a los usuarios que inicien la aplicación desde el menú **Inicio** en su lugar. En el procedimiento siguiente, se describe cómo deshabilitar la activación de URL.  
  
 Esta técnica se puede utilizar solo para las aplicaciones [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] instaladas en el equipo del usuario desde un servidor web. No se puede usar para aplicaciones solo en línea, que solo se pueden iniciar mediante su dirección URL. Para obtener más información acerca de la diferencia entre las aplicaciones solo en línea y las instaladas, vea [elegir una estrategia de implementación de ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md).  
  
 En este procedimiento se usa [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] . También puede realizar esta tarea mediante el [!INCLUDE[winsdklong](../includes/winsdklong-md.md)] . Para obtener más información, vea [Cómo: deshabilitar la activación de direcciones URL de aplicaciones ClickOnce](../deployment/how-to-disable-url-activation-of-clickonce-applications.md).  
  
## <a name="procedure"></a>Procedimiento  
  
#### <a name="to-disable-url-activation-for-your-application"></a>Deshabilitar la activación de direcciones URL para la aplicación  
  
1. Haga clic con el botón secundario en el nombre del proyecto en **Explorador de soluciones**y haga clic en **propiedades**.  
  
2. En la página **propiedades** , haga clic en la pestaña **publicar** .  
  
3. Haga clic en **Opciones**.  
  
4. Haga clic en **manifiestos**.  
  
5. Active la casilla **de verificación bloquear la aplicación para que no se active a través de una dirección URL**.  
  
6. Implementación de aplicación.  
  
## <a name="see-also"></a>Consulte también  
 [Publicar aplicaciones ClickOnce](../deployment/publishing-clickonce-applications.md)
