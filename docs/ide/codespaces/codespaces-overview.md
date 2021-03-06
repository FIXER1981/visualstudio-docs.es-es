---
title: Información general de GitHub Codespaces (versión preliminar)
description: Obtenga más información sobre GitHub Codespaces con Visual Studio y cómo puede ayudar a ampliar su entorno de desarrollo a la nube.
ms.topic: overview
ms.date: 09/04/2020
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
ms.workload:
- multiple
monikerRange: vs-2019
ms.openlocfilehash: 629ad64ad2a179e1f70998240f26a4484280e514
ms.sourcegitcommit: 09d1f5cef5360cdc1cdfd4b22a1a426b38079618
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "91005018"
---
# <a name="what-is-github-codespaces-preview"></a>¿Qué es GitHub Codespaces? (versión preliminar)

Le damos la bienvenida a Codespaces. Nos complace estar aquí.

GitHub Codespaces proporciona un entorno de desarrollo con tecnología de nube para cualquier actividad, ya sea un proyecto a largo plazo o una tarea a corto plazo, como la revisión de una solicitud de incorporación de cambios. Puede trabajar con un codespace desde Visual Studio 2019 Preview ([registrarse para la versión beta pública limitada](https://github.com/features/codespaces/signup-vs)).

Además, GitHub Codespaces ofrece muchas de las ventajas de DevOps, como la repetibilidad y la confiabilidad (que normalmente se han reservado para cargas de trabajo de producción) en un entorno de desarrollo. También puede personalizar Codespaces de GitHub para que las herramientas, los procesos y las configuraciones que prefiera y en los que confía estén ahí.

En este documento se explican los conceptos clave y se presentan las características de Codespaces. Si quiere empezar, consulte [Uso de Visual Studio con un codespace](use-visual-studio-with-codespaces.md).

> [!IMPORTANT]
> Debe suscribirse a la versión [beta pública](https://github.com/features/codespaces/signup-vs) limitada para usar GitHub Codespaces. Durante el período de la versión beta, GitHub no garantiza la disponibilidad de Codespaces. Para más información sobre cómo unirse a la versión beta, consulte [Acerca de Codespaces](https://docs.github.com/github/developing-online-with-codespaces/about-codespaces#joining-the-beta).

## <a name="concepts-and-features"></a>Conceptos y características

Las características de GitHub Codespaces se basan en algunos conceptos fundamentales. En esta sección se tratan esos conceptos y se ofrece un breve recorrido por las características.

### <a name="remote-development"></a>Desarrollo remoto

Hoy en día, muchos desarrolladores intentan codificar en configuraciones remotas o máquinas virtuales que están configuradas con pilas específicas de desarrollo y tiempo de ejecución. Lo hacen porque es demasiado difícil, demasiado problemático y, en algunos casos, casi imposible configurar estos entornos de desarrollo de forma local. Además, los usuarios quieren probar nuevas tecnologías o nuevos marcos sin el temor de "estropear" las máquinas que necesitan para su trabajo diario.

Aunque el uso de entornos remotos y herramientas compatibles con el sistema remoto aumenta las posibilidades de los desarrolladores, a menudo agrega la sobrecarga de la administración de máquinas. La configuración del entorno suele complicar la incorporación y el cambio de contexto. GitHub Codespaces elimina las barreras para la incorporación rápida y el cambio de contexto al permitir la coexistencia de muchos entornos al mismo tiempo. 

GitHub Codespaces proporciona soluciones administradas que le permiten centrarse en la productividad a través de la configuración. GitHub Codespaces amplía conceptual y técnicamente Visual Studio 2019 para el desarrollo remoto. 

### <a name="about-codespaces"></a>Acerca de los codespaces

Un codespace es la mitad de "back-end" de GitHub Codespaces. Es donde se produce todo el proceso asociado al desarrollo de software: compilación, depuración, restauración, etc. La creación de un codespace prepara todo lo necesario para completar una tarea, revisar una solicitud de incorporación de cambios o iniciar un nuevo proyecto. Los codespaces configuran el tiempo de ejecución, el compilador, el depurador, el editor, las configuraciones de dotfile personalizadas y el código fuente necesario para trabajar en un proyecto.

Los codespaces hospedados en la nube ofrecen las siguientes ventajas:

- Son rápidos de crear y descartables. Cree tantos como necesite (hasta los límites de la cuenta) y luego elimínelos cuando haya terminado.
- Son administrados, lo que reduce el mantenimiento general.
- Tienen precios predecibles y usted solo paga por lo que usa. Además, se ha incorporado la suspensión automática para eliminar los costos descontrolados.
- Ahorran recursos de proceso. Cuando se mueve la carga de trabajo de desarrollo a la nube, libera los recursos limitados de su máquina personal.

## <a name="custom-configuration"></a>Configuración personalizada

GitHub Codespaces se ha creado para dar cabida a la más amplia variedad de proyectos o tareas. Puede empezar con características de configuración inteligente que proporcionan valores predeterminados comunes o ajustar un codespace con [configuración personalizada](customize-codespaces.md).

La configuración flexible permite a los desarrolladores incorporarse rápidamente a proyectos con una configuración y unos requisitos únicos que son difíciles de aplicar en una máquina local. Además, los codespaces reproducibles eliminan los problemas de "funciona en mi máquina".

## <a name="personal-configuration"></a>Configuración personal

Sabemos que conservar las preferencias personales es decisivo para que el desarrollo en un codespace hospedado en la nube resulte y natural. GitHub Codespaces distribuye personalizaciones individuales en capas encima de la configuración de un codespace. GitHub Codespaces admite las preferencias y la configuración personales de los editores y los terminales.

Se puede crear un codespace con una colección de [dotfiles personalizados](https://docs.github.com/github/developing-online-with-codespaces/personalizing-codespaces-for-your-account) específica del usuario (por ejemplo, `.bashrc`, `.gitconfig`, etc.) y GitHub Codespaces sincroniza automáticamente la identidad, los temas y la configuración de Git, de modo que cada codespace que se cree tenga el aspecto y la apariencia que se quiera, independientemente de la funcionalidad del entorno específico del proyecto.

## <a name="see-also"></a>Consulte también

* [Uso de Visual Studio con un codespace](use-visual-studio-with-codespaces.md)
* [Personalización de un codespace](customize-codespaces.md)
* [Características de Visual Studio compatibles](supported-features-codespaces.md)
