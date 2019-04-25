---
title: Herramientas personalizadas | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, custom tools
- tools [Visual Studio], custom
- custom tools
ms.assetid: d669f154-9b23-48b6-b9f6-7419c8dd61a6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: dc6093d9bdbd780e1c8ddeb941f5f80dd479f77a
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56607608"
---
# <a name="custom-tools"></a>Herramientas personalizadas
*Herramientas personalizadas* le permiten asociar una herramienta con un elemento en un proyecto y ejecutar esa herramienta cada vez que se guarda el archivo. Determinadas herramientas personalizadas, a veces se denomina *generadores de un solo archivo*, con frecuencia se utilizan para implementar los traductores que generan código de los datos y viceversa. Por ejemplo, creación generadores de un solo archivo [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] y [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] código de fuente del *.settings* y *.resx* archivos. El código fuente generado proporciona acceso fuertemente tipado a los datos en el *.settings* y *.resx* archivos. El [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] y [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] tipos de proyectos admiten herramientas personalizadas; [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] tipos de proyectos no lo hacen. Sus propios tipos de proyecto también pueden admitir herramientas personalizadas.

 Las herramientas personalizadas son componentes registrados que implementan el `IVsSingleFileGenerator` interfaz.

 Herramientas personalizadas están asociadas con un `ProjectItem` objeto de la interfaz y son similares a los diseñadores y editores. Una herramienta personalizada toma el archivo representado por un `ProjectItem` como entrada y escribe un nuevo archivo cuyo nombre de archivo proporciona el `DefaultExtension` método.

## <a name="in-this-section"></a>En esta sección
- [Implementar generadores de un solo archivo](../../extensibility/internals/implementing-single-file-generators.md)

 Describe cómo utilizar el <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> interfaz para implementar una herramienta personalizada.

- [Registrar generadores de único archivo](../../extensibility/internals/registering-single-file-generators.md)

 Proporciona descripciones de todas las entradas del registro para una herramienta personalizada.

- [Exponer tipos a diseñadores visuales](../../extensibility/internals/exposing-types-to-visual-designers.md)

 Explica cómo los sistemas de proyecto proporcionan soporte técnico para los diseñadores visuales para acceso genera clases y tipos a través de los archivos ejecutables portables (PE) temporales.

- [Conservar la propiedad de un elemento de proyecto](../../extensibility/persisting-the-property-of-a-project-item.md)

 Muestra cómo conservar una propiedad de elemento de proyecto, como el autor de un archivo de código fuente, en el archivo de proyecto.

## <a name="reference"></a>Referencia
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> Proporciona detalles sobre la <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>, que transforma un archivo de entrada en un único archivo de salida que se compila o se agrega a un proyecto.

 <xref:EnvDTE.ProjectItem> Explica la `ProjectItem` interfaz, que representa un elemento en un proyecto.

 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A> Proporciona detalles sobre el `DefaultExtension` método, que recupera la extensión de nombre de archivo que se asigna al nombre del archivo de salida.

## <a name="related-sections"></a>Secciones relacionadas
- [Extender proyectos](../../extensibility/extending-projects.md)

 Describe cómo usar los proyectos y soluciones de [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] para organizar los archivos de código y de recursos, así como la implementación del control de código fuente.