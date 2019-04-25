---
title: Filtrar Exclusión de proyectos de una compilación
ms.date: 11/04/2016
ms.technology: vs-ide-compile
ms.topic: conceptual
ms.assetid: 17a837ca-5db9-46cd-b5a7-b14ad1d2c47d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ef85067ca3478bb2387f1f47a35938805f5fe0c5
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55924596"
---
# <a name="how-to-exclude-projects-from-a-build"></a>Filtrar Exclusión de proyectos de una compilación

Para compilar una solución no es necesario compilar todos los proyectos que contiene. Por ejemplo, se puede excluir un proyecto que interrumpa la compilación y, a continuación, compilar el proyecto tras haber investigado y resuelto los problemas.

Un proyecto se puede excluir de las siguientes maneras:

-   Eliminándolo temporalmente de la configuración de soluciones activa.

-   Creando una configuración de soluciones que no incluya el proyecto.

Para obtener más información, vea [Descripción de las configuraciones de compilación](../ide/understanding-build-configurations.md).

## <a name="to-temporarily-remove-a-project-from-the-active-solution-configuration"></a>Para eliminar temporalmente un proyecto de la configuración de soluciones activa

1.  En la barra de menús, elija **Compilar** > **Administrador de configuración**.

2.  En la tabla **Contextos del proyecto**, busque el proyecto que quiere excluir de la compilación.

3.  En la columna **Compilar** del proyecto, desactive la casilla.

4.  Pulse el botón **Cerrar** y, después, vuelva a compilar la solución.

## <a name="to-create-a-solution-configuration-that-excludes-a-project"></a>Para crear una configuración de soluciones que excluya un proyecto

1.  En la barra de menús, elija **Compilar** > **Administrador de configuración**.

2.  En la lista **Configuración de soluciones activas**, pulse **\<Nueva>**.

3.  En el cuadro **Nombre**, escriba un nombre para la configuración de soluciones.

4.  En la lista **Copiar configuración de**, pulse la configuración de soluciones en la que quiera basar la nueva configuración (por ejemplo, **Depurar**) y, después, pulse el botón **Aceptar**.

5.  En el cuadro de diálogo **Administrador de configuración**, desactive la casilla de la columna **Compilar** del proyecto que quiera excluir y, después, pulse el botón **Cerrar**.

6.  En la barra de herramientas **Estándar**, compruebe que la nueva configuración de soluciones sea la configuración activa en el cuadro **Configuraciones de soluciones**.

7.  En la barra de menús, elija **Compilación** > **Recompilar solución**.

## <a name="see-also"></a>Vea también

- [Descripción de las configuraciones de compilación](../ide/understanding-build-configurations.md)
- [Cómo: Crear y editar configuraciones](../ide/how-to-create-and-edit-configurations.md)
- [Cómo: Compilación de varias configuraciones simultáneamente](../ide/how-to-build-multiple-configurations-simultaneously.md)