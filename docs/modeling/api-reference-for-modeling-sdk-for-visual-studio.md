---
title: Referencia de API para modelar el SDK
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6be903b2d0e269a0bce99ab57ff83e1b4bf8caa7
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55946074"
---
# <a name="api-reference-for-modeling-sdk-for-visual-studio"></a>Referencia de API para modelar el SDK de Visual Studio

El SDK de modelado y visualización de Visual Studio proporciona la plataforma en la que se generan las herramientas de lenguajes específicos de dominio (DSL).

Esta sección contiene material de referencia para espacios de nombres que tienen nombres que comienzan con "Microsoft.VisualStudio.Modeling".

|Espacio de nombres|Contenido|
|-|-|
|<xref:Microsoft.VisualStudio.Modeling?displayProperty=fullName>|Clases como ModelElement, que es la clase base de todas las clases de dominio que se definen en un DSL.|
|<xref:Microsoft.VisualStudio.Modeling.Design?displayProperty=fullName>|Las clases que forman parte de una definición de DSL.|
|<xref:Microsoft.VisualStudio.Modeling.Diagnostics?displayProperty=fullName>|Las herramientas de medición modelo Visor Store y el rendimiento.|
|<xref:Microsoft.VisualStudio.Modeling.Diagrams?displayProperty=fullName>|Clases como ShapeElement, que es la clase base de todas las formas que se definen en un DSL.|
|<xref:Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement?displayProperty=fullName>|Métodos de gesto y selección.|
|<xref:Microsoft.VisualStudio.Modeling.DslDefinition?displayProperty=fullName>|La API del Diseñador de definición de DSL.|
|<xref:Microsoft.VisualStudio.Modeling.DslDefinition.Design?displayProperty=fullName>|Clases internas del Diseñador de definición de DSL.|
|<xref:Microsoft.VisualStudio.Modeling.DslDefinition.ExtensionEnablement?displayProperty=fullName>|Atributos que permiten ampliar el Diseñador de DSL con comandos, gestos y validación.|
|<xref:Microsoft.VisualStudio.Modeling.Extensibility?displayProperty=fullName>|Métodos de extensión para ModelElement que implementan la extensibilidad de DSL.|
|<xref:Microsoft.VisualStudio.Modeling.ExtensionEnablement?displayProperty=fullName>|Atributos de extensibilidad|
|<xref:Microsoft.VisualStudio.Modeling.Immutability?displayProperty=fullName>|Le permite hacer que partes de un modelo de solo lectura.|
|<xref:Microsoft.VisualStudio.Modeling.Integration?displayProperty=fullName>|La API de Modelbus, que le ayuda a integrar modelos diferentes.|
|<xref:Microsoft.VisualStudio.Modeling.Integration.Picker?displayProperty=fullName>|El cuadro de diálogo que permite a los usuarios navegar a los modelos y elementos para crear referencias de Modelbus.|
|<xref:Microsoft.VisualStudio.Modeling.Integration.Picker.Hosting?displayProperty=fullName>|El servicio de selector.|
|<xref:Microsoft.VisualStudio.Modeling.Integration.Shell?displayProperty=fullName>|Entorno de adaptador de ModelBus de Visual Studio.|
|<xref:Microsoft.VisualStudio.Modeling.Integration.Shell.Picker?displayProperty=fullName>|El cuadro de diálogo de selector que permite a los usuarios navegar a los modelos y elementos para crear referencias de Modelbus.|
|<xref:Microsoft.VisualStudio.Modeling.Shell?displayProperty=fullName>|La interfaz entre lenguajes DSL y Visual Studio.|
|<xref:Microsoft.VisualStudio.Modeling.Shell.ExtensionEnablement?displayProperty=fullName>|Le permite definir comandos del menú contextual (contexto).|
|<xref:Microsoft.VisualStudio.Modeling.Validation?displayProperty=fullName>|Le permite definir restricciones de validación.|

## <a name="see-also"></a>Vea también

- [Personalizar la transformación de texto T4](../modeling/customizing-t4-text-transformation.md)
