---
title: Extensibilidad del servicio de lenguaje heredado | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- language services
- Visual Studio, language services
ms.assetid: 2700cd4d-5f68-43fc-b62f-dc80c3f3aa85
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 81b5ec3de8d7b0b9466e162c3ee193c130634cd4
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80707409"
---
# <a name="legacy-language-service-extensibility"></a>Extensibilidad de servicio de lenguaje heredado
Un servicio de lenguaje proporciona compatibilidad específica del lenguaje para editar el código fuente en el IDE.

 Los servicios de lenguaje heredados se implementan como parte de un VSPackage, pero la forma más reciente de implementar las características del servicio de lenguaje es usar extensiones de MEF. Para obtener más información sobre la nueva manera de implementar un servicio de lenguaje, vea [Editor y extensiones del servicio de lenguaje](../../extensibility/editor-and-language-service-extensions.md).

 En esta sección se describe la estructura y la implementación de un servicio de lenguaje heredado.

## <a name="in-this-section"></a>En esta sección
- [Migración de un servicio de lenguaje heredado](../../extensibility/internals/migrating-a-legacy-language-service.md)

 Explica cómo actualizar un servicio de lenguaje de Visual Studio 2008 a la versión más reciente.

- [Fundamentos de servicio de lenguaje heredado](../../extensibility/internals/legacy-language-service-essentials.md)

 Proporciona información importante sobre cómo desarrollar servicios de lenguaje para integrar un lenguaje de programación en Visual Studio.

- [Desarrollo de un servicio de lenguaje heredado](../../extensibility/internals/developing-a-legacy-language-service.md)

 Proporciona vínculos a temas que pueden ayudarle a crear un servicio de lenguaje.

- [Colores de la sintaxis en un servicio de lenguaje heredado](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)

 Proporciona información sobre cómo admitir el resaltado de sintaxis en un servicio de lenguaje.

- [Implementación de un servicio de lenguaje heredado](../../extensibility/internals/implementing-a-legacy-language-service1.md)

 Proporciona información sobre cómo usar Managed Package Framework (MPF) para implementar un servicio de lenguaje completo en código administrado.

- [Compatibilidad con herramientas de exploración de símbolos](../../extensibility/internals/supporting-symbol-browsing-tools.md)

 Describe las bibliotecas y herramientas que permiten examinar vistas de árbol de símbolos en el IDE.

## <a name="related-sections"></a>Secciones relacionadas
- [Editor y extensiones de servicio de lenguaje](../../extensibility/editor-and-language-service-extensions.md)

 Proporciona información general sobre los editores de Visual Studio.

- [Compatibilidad del servicio de lenguaje con la depuración](../../extensibility/internals/language-service-support-for-debugging.md)

 Proporciona información sobre y un vínculo al SDK de depuración de Visual Studio, que contiene la información necesaria para crear y personalizar los componentes del depurador que se usan para depurar programas.
