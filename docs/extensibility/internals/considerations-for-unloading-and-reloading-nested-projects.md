---
title: Descargar y volver a cargar proyectos anidados
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- nested projects, unloading and reloading
- projects [Visual Studio SDK], unloading and reloading nested
ms.assetid: 06c3427e-c874-45b1-b9af-f68610ed016c
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 154eb51014d9719b601cf87d53383f57941403a8
ms.sourcegitcommit: 4ae5e9817ad13edd05425febb322b5be6d3c3425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2020
ms.locfileid: "90036826"
---
# <a name="considerations-for-unloading-and-reloading-nested-projects"></a>Consideraciones para descargar y volver a cargar proyectos anidados

Al implementar tipos de proyecto anidados, debe realizar pasos adicionales al descargar y volver a cargar los proyectos. Para notificar correctamente a los agentes de escucha los eventos de la solución, debe generar correctamente los `OnBeforeUnloadProject` `OnAfterLoadProject` eventos y.

Una razón para generar estos eventos es para el control de código fuente (SCC). No quiere que SCC elimine los elementos del servidor y, a continuación, los vuelva a agregar como *nuevo* si hay una `Get` operación de SCC. En ese caso, un archivo nuevo se cargará fuera de SCC. Tendrá que descargar y volver a cargar todos los archivos por si son diferentes.

Llamadas de control de código fuente `ReloadItem` . Implemente la <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents> interfaz para llamar a `OnBeforeUnloadProject` y `OnAfterLoadProject` eliminar el proyecto y volver a crearlo. Al implementar la interfaz de esta manera, se informa a SCC de que el proyecto se eliminó temporalmente y se volvió a agregar. Por lo tanto, SCC no funciona en el proyecto como si el proyecto se eliminara *realmente* y se volviera a agregar.

## <a name="reload-projects"></a>Volver a cargar proyectos

Para admitir la recarga de proyectos anidados, se implementa el <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> método. En la implementación de `ReloadItem` , se cierran los proyectos anidados y, a continuación, se vuelven a crear.

Normalmente, cuando se recarga un proyecto, el IDE genera los <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnBeforeUnloadProject%2A> eventos y <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterLoadProject%2A> . Sin embargo, en el caso de los proyectos anidados que se eliminan y se recargan, el proyecto primario inicia el proceso, no el IDE. Dado que el proyecto primario no genera eventos de la solución y el IDE no tiene información sobre la inicialización del proceso, no se generan los eventos.

Para controlar este proceso, el proyecto primario llama a `QueryInterface` en la <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents> interfaz. `IVsFireSolutionEvents` tiene funciones que indican al IDE que genere el `OnBeforeUnloadProject` evento para descargar el proyecto anidado y, a continuación, genere el `OnAfterLoadProject` evento para volver a cargar el mismo proyecto.

## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>
- [Anidar proyectos](../../extensibility/internals/nesting-projects.md)
