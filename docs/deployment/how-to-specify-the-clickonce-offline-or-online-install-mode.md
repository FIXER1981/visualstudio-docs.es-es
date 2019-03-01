---
title: 'Cómo: especificar la sin conexión de ClickOnce o instalar el modo en línea | Microsoft Docs'
ms.date: 11/04/2016
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 786b187aa38aaeb49f840e28f25ec3cc43087ce8
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56625392"
---
# <a name="how-to-specify-the-clickonce-offline-or-online-install-mode"></a>Cómo: Especificar el modo de instalación en línea y sin conexión de ClickOnce
El `Install Mode` para un [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplicación determina si la aplicación estará disponible en línea o sin conexión. Cuando se elige **la aplicación solo está disponible en línea**, el usuario debe tener acceso a la [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ubicación (una página Web o un recurso compartido de archivos) para ejecutar la aplicación de publicación. Cuando se elige **la aplicación también está disponible sin conexión**, la aplicación agrega entradas a la **iniciar** menú y el **agregar o quitar programas** cuadro de diálogo; el usuario es puede ejecutar la aplicación cuando no están conectados.

 El `Install Mode` se pueden establecer en el **publicar** página de la **Diseñador de proyectos**.

 **Tenga en cuenta** el `Install Mode` también se puede establecer mediante el Asistente para publicación. Para obtener más información, consulte [Cómo: publicar una aplicación ClickOnce mediante el Asistente para publicación](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).

### <a name="to-make-a-clickonce-application-available-online-only"></a>Para que una aplicación ClickOnce esté disponible solo en línea

1.  Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**.

2.  Haga clic en la pestaña **Publicar**.

3.  En el **instalar el modo y configuración** área, haga clic en el **la aplicación solo está disponible en línea** botón de opción.

### <a name="to-make-a-clickonce-application-available-online-or-offline"></a>Para que una aplicación ClickOnce esté disponible en línea o sin conexión

1.  Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**.

2.  Haga clic en la pestaña **Publicar**.

3.  En el **instalar el modo y configuración** área, haga clic en el **la aplicación también está disponible sin conexión** botón de opción.

     Cuando se instala, la aplicación agrega entradas a la **iniciar** menú y a **agregar o quitar programas** en el Panel de Control.

## <a name="see-also"></a>Vea también
- [Publicar aplicaciones ClickOnce](../deployment/publishing-clickonce-applications.md)
- [Cómo: Publicar una aplicación ClickOnce mediante el Asistente para publicación](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
- [Selección de una estrategia de implementación de ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md)