---
title: Validar el sistema durante el desarrollo
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ce0822f5731e7c09a6f6dff9116e70b97a529206
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2019
ms.locfileid: "56316761"
---
# <a name="validate-your-system-during-development"></a>Validar el sistema durante el desarrollo
Visual Studio puede ayudarle a mantener la coherencia del software con los requisitos de los usuarios y con la arquitectura del sistema.

 Para ver las versiones de Visual Studio compatibles con cada característica, consulte [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="key-tasks"></a>Tareas clave
 Use las tareas siguientes para validar el software.

|**Tareas**|**Temas relacionados**|
|-|-|
|**Asegúrese de que el software cumple los requisitos de los usuarios**:<br /><br /> Puede usar modelos arquitectónicos y modelos de requisitos que le ayuden a organizar las pruebas del sistema y sus componentes. Con esta práctica, tendrá la certeza de que incluye en la prueba los requisitos que son importantes para los usuarios y otras partes interesadas, y podrá actualizar las pruebas rápidamente cuando cambien los requisitos.|-   [Desarrollar pruebas en un modelo](../modeling/develop-tests-from-a-model.md)|
|**Asegúrese de que el software mantiene la coherencia con el diseño previsto del sistema:**<br /><br /> Diagramas de dependencia describen las dependencias previstas entre los componentes de la aplicación. Durante el desarrollo, puede comprobar si las dependencias reales del código se ajustan al diseño previsto.|-   [Crear diagramas de dependencia desde el código](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [Validar código con diagramas de dependencia](../modeling/validate-code-with-layer-diagrams.md)|

## <a name="external-resources"></a>Recursos externos

|**Categoría**|**Vínculos**|
|-|-|
|**Vídeos**|![vínculo a vídeo](../data-tools/media/playvideo.gif) [Channel 9: Doug Seven: Comprensión del código y diseño del sistema con Visual Studio 2010](http://go.microsoft.com/fwlink/?LinkId=216100)<br /><br /> ![vínculo a vídeo](../data-tools/media/playvideo.gif) [Channel 9: Diseñar una aplicación con un diagrama de dependencia](http://go.microsoft.com/fwlink/?LinkID=201117)<br /><br /> ![vínculo a vídeo](../data-tools/media/playvideo.gif) [MSDN How Do I Series: Cómo validar código con diagramas de dependencia](http://go.microsoft.com/fwlink/?LinkID=214405)|
|**Foros**|-   [Herramientas de visualización y modelado de Visual Studio](http://go.microsoft.com/fwlink/?LinkId=184720)<br />-   [SDK de visualización y modelado de Visual Studio (Herramientas DSL)](http://go.microsoft.com/fwlink/?LinkId=184721)|
|**Blogs**|-   [Microsoft DevOps](https://devblogs.microsoft.com/devops/)|
|**Artículos y diarios técnicos**|[Centro de arquitectura - MSDN](http://go.microsoft.com/fwlink/?LinkId=201343)|

## <a name="see-also"></a>Vea también

- [Probar la aplicación](/azure/devops/test/overview?view=vsts)
- [Requisitos del usuario de modelos](../modeling/model-user-requirements.md)
- [Analizar y modelar la arquitectura](../modeling/analyze-and-model-your-architecture.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
