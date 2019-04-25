---
title: Procedimiento Establecer permisos personalizados para una aplicación ClickOnce | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce applications, permissions
- permissions, ClickOnce applications
ms.assetid: 660459ca-ef73-44a8-b323-610001f63b93
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d275875b18941df63e0f6ee3c17f427334eab88a
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "60058549"
---
# <a name="how-to-set-custom-permissions-for-a-clickonce-application"></a>Procedimiento Establecimiento de permisos personalizados para una aplicación ClickOnce
Puede implementar una aplicación [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] que use los permisos predeterminados de las zonas de Internet o de la intranet local. Como alternativa, puede crear una zona personalizada para los permisos específicos necesarios para la aplicación. Para ello, personalice los permisos de seguridad en la página **Seguridad** del **Diseñador de proyectos**.

### <a name="to-customize-a-permission"></a>Para personalizar un permiso

1. Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**.

2. Haga clic en la pestaña **Seguridad** .

3. Active la casilla **Habilitar configuración de seguridad de ClickOnce** .

4. Seleccione el botón de la opción **Aplicación de confianza parcial** .

     Los controles de la sección **Permisos de seguridad de ClickOnce** están habilitados.

5. En la lista desplegable **Zona desde la que se instalará la aplicación** , haga clic en **(Personalizada)**.

6. Haga clic en **Editar XML de permisos**.

     El archivo *app.manifest* se abrirá en el Editor XML.

7. Antes del elemento `</applicationRequestMinimum>` , agregue el código XML de los permisos necesarios para la aplicación.

    > [!NOTE]
    >  Puede usar el método `ToXml` de un conjunto de permisos para generar el código XML del manifiesto de la aplicación. Por ejemplo, para generar el XML del conjunto de permisos <xref:System.Security.Permissions.EnvironmentPermission> , llame al método <xref:System.Security.Permissions.EnvironmentPermission.ToXml%2A> .

## <a name="see-also"></a>Vea también
- [Proteger aplicaciones ClickOnce](../deployment/securing-clickonce-applications.md)
- [Seguridad de acceso del código para aplicaciones ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)
