---
title: 'Cómo: especificar un nombre de menú de inicio para una aplicación ClickOnce | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Start menu resource name
- Start menu name
- ClickOnce deployment, Start menu name
ms.assetid: 4b5183b2-2fd4-4433-9310-4a73bb12c4e3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3ab55674cd1de54881eb46b47997a943678cbacd
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56635623"
---
# <a name="how-to-specify-a-start-menu-name-for-a-clickonce-application"></a>Cómo: Especificar un nombre en el menú Inicio para una aplicación ClickOnce
Cuando un [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] se instala la aplicación para su uso en línea y sin conexión, se agrega una entrada para el **iniciar** menú y el **agregar o quitar programas** lista. De forma predeterminada, el nombre para mostrar es el mismo que el nombre del ensamblado de la aplicación, pero puede cambiar el nombre para mostrar estableciendo **nombre de producto** en el **opciones de publicación** cuadro de diálogo.

 **Nombre de producto** se mostrará en el *publish.htm* página; para una aplicación instalada sin conexión, será el nombre de la entrada en el **iniciar** menú y, también será el nombre que se muestra en **Agregar o quitar programas**.

 **Nombre del publicador** aparecerá en la *publish.htm* página anterior **nombre de producto**, y para una aplicación instalada sin conexión, también será el nombre de la carpeta que contiene la aplicación icono de la **iniciar** menú.

 Se crea la referencia de aplicación o de método abreviado de menú Inicio en *%appdata%\Microsoft\Windows\Start Inicio\Programas\\< nombre del publicador\>*. La referencia de método abreviado o la aplicación tiene el mismo nombre que el nombre del producto.

 Puede establecer el **nombre de producto** y **nombre del publicador** propiedades en el **opciones de publicación** cuadro de diálogo, disponible en el **publicar** página de la **Diseñador de proyectos**.

### <a name="to-specify-a-start-menu-name"></a>Para especificar un nombre de menú Inicio

1.  Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**.

2.  Haga clic en la pestaña **Publicar**.

3.  Haga clic en el **opciones** botón para abrir el **opciones de publicación** cuadro de diálogo.

4.  Haga clic en **descripción**.

5.  En el **opciones de publicación** diálogo cuadro, escriba el nombre para mostrar en **nombre de producto**.

6.  Si lo desea, puede escribir un nombre de publicador en **nombre del publicador**.

## <a name="see-also"></a>Vea también
- [Publicar aplicaciones ClickOnce](../deployment/publishing-clickonce-applications.md)
- [Cómo: Publicar una aplicación ClickOnce mediante el Asistente para publicación](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)