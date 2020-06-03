---
title: Uso de Visual Studio en una máquina virtual de Azure
titleSuffix: ''
description: Aprenda a usar Visual Studio en una máquina virtual de Azure
ms.date: 04/23/2020
ms.custom: seodec18
ms.topic: conceptual
helpviewer_keywords:
- azure services
- virtual machine
- installation
- visual studio
author: ornellaalt
ms.author: ornella
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 6453c263cb970ae3fff2c134f1ae570bca730b93
ms.sourcegitcommit: d20ce855461c240ac5eee0fcfe373f166b4a04a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84183241"
---
# <a name="visual-studio-images-on-azure"></a><a id="top"> </a> Imágenes de Visual Studio en Azure

El uso de Visual Studio en una máquina virtual de Azure preconfigurada es una forma fácil y rápida de llegar a un entorno de desarrollo en funcionamiento partiendo de cero. Hay imágenes del sistema con distintas configuraciones de Visual Studio disponibles en [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/category/compute?filters=virtual-machine-images%3Bmicrosoft%3Bwindows&page=1&subcategories=application-infrastructure).

¿Es la primera vez que usa Azure? [Cree una cuenta gratuita de Azure](https://azure.microsoft.com/free).

## <a name="what-configurations-and-versions-are-available"></a>¿Qué configuraciones y versiones están disponibles?

En Azure Marketplace puede encontrar imágenes de las versiones principales más recientes: Visual Studio 2019, Visual Studio 2017 y Visual Studio 2015.  En cada versión principal que se lance, verá la versión de lanzamiento original "lanzada en web" (RTW) y las últimas versiones actualizadas.  Cada una de estas versiones ofrece las ediciones Visual Studio Enterprise y Visual Studio Community.  Estas imágenes se actualizan como mínimo cada mes para incluir las actualizaciones más recientes de Visual Studio y Windows.  Aunque los nombres de las imágenes siguen siendo los mismos, la descripción de cada imagen incluye la versión del producto instalada y la fecha de inicio de la imagen.

| Versión de lanzamiento                                                                                                                                          | Ediciones              |    Versión del producto    |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------:|:---------------------:|:-----------------------:|
| [Visual Studio 2019: Más reciente (versión 16.5)](https://azuremarketplace.microsoft.com/marketplace/apps/microsoftvisualstudio.visualstudio2019latest?tab=Overview) | Enterprise, Community | Versión 16.5.4    |
| Visual Studio 2019: RTW                         | Empresa            | Versión 16.0.13    |
| Visual Studio 2017: Versión más reciente (15.9)           | Enterprise, Community | Versión 15.9.22   |
| Visual Studio 2017: RTW                             | Enterprise, Community | Versión 15.0.28   |
| Visual Studio 2015: Más reciente (actualización 3)              | Enterprise, Community | Versión 14.0.25431.01 |

> [!NOTE]
> De conformidad con la directiva de mantenimiento de Microsoft, el servicio de mantenimiento de la versión de lanzamiento original ("RTW") de Visual Studio 2015 ha expirado. Visual Studio 2015 Update 3 es la única versión que se ofrece con la línea de productos de Visual Studio 2015.

Para más información, consulte la [directiva de mantenimiento de Visual Studio](/visualstudio/productinfo/vs-servicing-vs).

## <a name="what-features-are-installed"></a>¿Qué características están instaladas?

Cada imagen contiene el conjunto de características recomendado para esa edición de Visual Studio. Por lo general, la instalación incluye:

* Todas las cargas de trabajo disponibles que incluyan los componentes opcionales recomendados para cada carga de trabajo
* SDK, paquetes de destino y herramientas de desarrollo de .NET 4.6.2 y .NET 4.7
* Visual F#
* Extensión de GitHub para Visual Studio
* Herramientas de LINQ to SQL

Se utiliza la línea de comandos siguiente para instalar Visual Studio al compilar las imágenes:

```shell
    vs_enterprise.exe --allWorkloads --includeRecommended --passive ^
       --add Microsoft.Net.Component.4.7.SDK ^
       --add Microsoft.Net.Component.4.7.TargetingPack ^
       --add Microsoft.Net.Component.4.6.2.SDK ^
       --add Microsoft.Net.Component.4.6.2.TargetingPack ^
       --add Microsoft.Net.ComponentGroup.4.7.DeveloperTools ^
       --add Microsoft.VisualStudio.Component.FSharp ^
       --add Component.GitHub.VisualStudio ^
       --add Microsoft.VisualStudio.Component.LinqToSql
```

Si las imágenes no incluyen la característica de Visual Studio que necesita, envíe un comentario mediante la herramienta para crear comentarios que se encuentra en la esquina superior derecha de la página.

## <a name="what-size-vm-should-i-choose"></a>¿Qué tamaño de máquina virtual debería elegir?

Azure ofrece una amplia gama de tamaños de máquina virtual. Dado que Visual Studio es una eficaz aplicación multiproceso, es recomendable que la máquina tenga un tamaño que pueda incluir al menos dos procesadores y 7 GB de memoria. Le recomendamos los siguientes tamaños de máquina virtual para las imágenes de Visual Studio:

* Standard_D2_v3
* Standard_D2s_v3
* Standard_D4_v3
* Standard_D4s_v3
* Standard_D2_v2
* Standard_D2S_v2
* Standard_D3_v2

Para más información sobre los tamaños de máquina más recientes, consulte [Tamaños de las máquinas virtuales Windows en Azure](/azure/virtual-machines/windows/sizes).

Con Azure puede reequilibrar su opción inicial cambiando el tamaño de la máquina virtual. También puede aprovisionar una nueva máquina virtual con un tamaño más adecuado o cambiar el tamaño de la máquina virtual existente en otro hardware subyacente. Para más información, consulte [Cambio de tamaño de una máquina virtual Windows](/azure/virtual-machines/windows/resize-vm).

## <a name="after-the-vm-is-running-whats-next"></a>Una vez que la máquina virtual se esté ejecutando, ¿qué tengo que hacer?

Visual Studio sigue el modelo "traiga su propia licencia" de Azure. Al igual que sucede en la instalación de hardware propietario, uno de los primeros pasos es obtener una licencia para la instalación de Visual Studio. Para desbloquear Visual Studio escoja una de estas dos opciones:
- Iniciar sesión con una cuenta Microsoft que esté asociada con una suscripción de Visual Studio
- Desbloquear Visual Studio con la clave de producto suministrada con la compra inicial

Para obtener más información, consulte [Iniciar sesión en Visual Studio](../ide/signing-in-to-visual-studio.md) y [Cómo desbloquear Visual Studio](../ide/how-to-unlock-visual-studio.md).

## <a name="how-do-i-save-the-development-vm-for-future-or-team-use"></a>¿Cómo puedo guardar la máquina virtual de desarrollo para un uso futuro o del equipo?

Hay una amplia gama de entornos de desarrollo y, si quiere compilar uno de los entornos más complejos, esto le supondrá un costo significativo. Independientemente de la configuración de su entorno, puede guardar o capturar la máquina virtual configurada como una "imagen base" para un uso futuro o para otros miembros del equipo. Después, al arrancar la nueva máquina virtual, se aprovisionará a partir de la imagen base y no de la imagen de Azure Marketplace.

Un resumen rápido: use la herramienta de preparación del sistema (Sysprep) y apague la máquina virtual en ejecución y, luego, capture *(Figura 1)* la máquina virtual como imagen mediante la interfaz de usuario de Azure Portal. Azure guarda el archivo `.vhd` que contiene la imagen en la cuenta de almacenamiento que se elija. Después, la nueva imagen aparecerá como recurso de imagen en la lista de recursos de la suscripción.

![Captura de una imagen mediante la interfaz de usuario de Azure Portal.](media/capture-vm.png)

*(Figura 1) Captura de una imagen mediante la interfaz de usuario de Azure Portal.*

Para obtener más información, consulte [Captura de una imagen administrada de una máquina virtual generalizada en Azure](/azure/virtual-machines/windows/capture-image-resource).

> [!IMPORTANT]
> No olvide usar Sysprep para preparar la máquina virtual. Si se salta este paso, Azure no podrá aprovisionar una máquina virtual a partir de la imagen.

> [!NOTE]
> Se sigue generando algún costo por el almacenamiento de las imágenes, pero ese costo incremental puede ser insignificante en comparación con los costos de sobrecarga para recompilar la máquina virtual desde el principio para cada persona del equipo que necesite una. Por ejemplo, crear y almacenar una imagen de 127 GB durante un mes que todo el equipo pueda reutilizar cuesta unos cuantos dólares. Sin embargo, estos costos son insignificantes en comparación con las horas que invierte cada empleado en compilar y validar un paquete de desarrollo configurado correctamente para su uso individual.

Además, puede que las tecnologías o las tareas de desarrollo requieran mayor escalado (como variedades de configuraciones de desarrollo y varias configuraciones de máquina). Puede usar Azure DevTest Labs para crear _recetas_ que automatizan la construcción de la "imagen perfecta". También puede utilizar DevTest Labs para administrar directivas para las máquinas virtuales en ejecución del equipo. [Uso de Azure DevTest Labs para desarrolladores](/azure/devtest-lab/devtest-lab-developer-lab) es la mejor fuente de información sobre DevTest Labs.

## <a name="next-steps"></a>Pasos siguientes

Ahora que ya está informado sobre las imágenes preconfiguradas de Visual Studio, el siguiente paso es crear una máquina virtual:

* [Creación de una máquina virtual en Azure Portal](/azure/virtual-machines/windows/quick-create-portal)
* [Información general sobre las máquinas virtuales Windows](/azure/virtual-machines/windows/overview)
