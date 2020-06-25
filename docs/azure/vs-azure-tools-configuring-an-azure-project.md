---
title: Configuración de un proyecto de servicio en la nube de Azure
description: Aprenda a configurar un proyecto de servicio en la nube de Azure en Visual Studio dependiendo de los requisitos para dicho proyecto.
author: ghogen
manager: jillfra
assetId: 609d6965-05cc-47b1-82dc-c76a92d4f295
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: how-to
ms.date: 03/06/2017
ms.author: ghogen
ms.openlocfilehash: 1776aebbe827295cbc7902f72417bc57e03a4196
ms.sourcegitcommit: 1d4f6cc80ea343a667d16beec03220cfe1f43b8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85280640"
---
# <a name="configure-an-azure-cloud-service-project-with-visual-studio"></a>Configuración de un proyecto de servicio en la nube de Azure con Visual Studio
Es posible configurar un proyecto de servicio en la nube de Azure dependiendo de los requisitos para dicho proyecto. Puede establecer las propiedades del proyecto para las siguientes categorías:

- **Publicar un servicio en la nube en Azure**: Puede establecer una propiedad para asegurarse de que no se elimina accidentalmente un servicio en la nube existente implementado en Azure.
- **Ejecutar o depurar un servicio en la nube en el equipo local**: Puede seleccionar una configuración del servicio para usarla e indicar si desea iniciar el emulador de almacenamiento de Azure.
- **Validar un paquete de servicio en la nube cuando se crea**: Puede decidir si desea tratar las advertencias como errores para asegurarse de que el paquete de servicio en la nube se implementa sin ningún problema.

## <a name="steps-to-configure-an-azure-cloud-service-project"></a>Pasos para configurar un proyecto de servicio en la nube de Azure
1. Abra o cree un proyecto de servicio en la nube en Visual Studio.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, en el menú contextual, seleccione **Propiedades**.

1. En la página de propiedades del proyecto, seleccione la pestaña **Desarrollo**.

    ![Menú Propiedades del proyecto](./media/vs-azure-tools-configuring-an-azure-project/solution-explorer-project-properties-menu.png)

1. Establezca **Preguntar antes de eliminar una implementación existente** en **True**. Esta configuración le ayuda a asegurarse de que no elimina accidentalmente una implementación existente en Azure.

1. Seleccione la opción que desee en **Configuración de servicio** para indicar qué configuración de servicio desea usar al ejecutar o depurar el servicio en la nube de manera local. Para más información sobre cómo modificar una configuración de servicio para un rol, vea [Configuración de los roles para un servicio de Azure con Visual Studio](./vs-azure-tools-configure-roles-for-cloud-service.md).

1. Establezca **Iniciar emulador de almacenamiento de Azure** en **True** para iniciar el emulador de almacenamiento de Azure al ejecutar o depurar el servicio en la nube de manera local.

1. Establezca **Tratar advertencias como errores** en **True** para asegurarse de que no se puede publicar si hay errores de validación del paquete.

1. Establezca **Usar puertos de proyectos web** en **True** para asegurarse de que el rol web usa el mismo puerto cada vez que se inicia de manera local en IIS Express.

1. En la barra de herramientas de Visual Studio, seleccione **Guardar**.

## <a name="next-steps"></a>Pasos siguientes
- [Configuración de un proyecto de Azure mediante varias configuraciones de servicio](vs-azure-tools-multiple-services-project-configurations.md)
