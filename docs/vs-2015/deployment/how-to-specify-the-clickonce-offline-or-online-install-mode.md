---
title: 'Cómo: especificar el modo de instalación en línea o sin conexión de ClickOnce | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, specifying install mode
- install mode
- online applications
- offline applications
- ClickOnce install mode
ms.assetid: 0aee5fc1-e966-4bda-9b8f-d9997aeaa779
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d4111ca5aee4a405a4a797dbfee14a3d4b50435f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68149755"
---
# <a name="how-to-specify-the-clickonce-offline-or-online-install-mode"></a>Cómo: Especificar el modo de instalación en línea y sin conexión de ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

El `Install Mode` para una [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplicación determina si la aplicación estará disponible sin conexión o en línea. Cuando elija **la aplicación solo está disponible en línea**, el usuario debe tener acceso a la [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] Ubicación de publicación (una página web o un recurso compartido de archivos) para poder ejecutar la aplicación. Cuando se elige **la aplicación también está disponible sin conexión**, la aplicación agrega entradas al menú **Inicio** y al cuadro de diálogo **Agregar o quitar programas** . el usuario puede ejecutar la aplicación cuando no está conectada.  
  
 `Install Mode`Se puede establecer en la página **publicar** del diseñador de **proyectos**.  
  
 **Nota:** `Install Mode` También se puede establecer mediante el Asistente para publicación. Para obtener más información, consulte [Cómo: publicar una aplicación ClickOnce mediante el Asistente para publicación](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
### <a name="to-make-a-clickonce-application-available-online-only"></a>Para que una aplicación ClickOnce esté disponible solo en línea  
  
1. Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**.  
  
2. Haga clic en la pestaña **Publicar**.  
  
3. En el área **modo de instalación y configuración** , haga clic en el botón de opción **la aplicación solo está disponible en línea** .  
  
### <a name="to-make-a-clickonce-application-available-online-or-offline"></a>Para que una aplicación ClickOnce esté disponible en línea o sin conexión  
  
1. Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**.  
  
2. Haga clic en la pestaña **Publicar**.  
  
3. En el área **modo de instalación y configuración** , haga clic en el botón de opción **la aplicación también está disponible sin conexión** .  
  
     Cuando se instala, la aplicación agrega entradas al menú **Inicio** y a **Agregar o quitar programas** en el panel de control.  
  
## <a name="see-also"></a>Consulte también  
 [Publicar aplicaciones ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Cómo: publicar una aplicación ClickOnce mediante el Asistente para publicación](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [Elegir una estrategia de implementación ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md)
