---
title: Caracteres especiales de MSBuild | Microsoft Docs
ms.date: 06/12/2019
ms.topic: conceptual
helpviewer_keywords:
- escape characters
- escape
- MSBuild Escape Characters
ms.assetid: 545e6a59-1093-4514-935e-78679a46fb3c
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fdc9024db06fe27fab5dfdf9589300a6eb671368
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "77633218"
---
# <a name="msbuild-special-characters"></a>Caracteres especiales de MSBuild

MSBuild reserva algunos caracteres para usos especiales en contextos concretos. Para usar dichos caracteres literalmente en el contexto en el que están reservados, debe aplicarles secuencias de escape. Por ejemplo, un asterisco tiene un significado especial solo en los atributos `Include` y `Exclude` de una definición de elemento y en las llamadas a `CreateItem`. Si quiere que aparezca como un asterisco en uno de estos contextos, debe aplicarle una secuencia de escape. En todos los demás contextos, simplemente escriba el asterisco donde quiera que aparezca.

 Para aplicar una secuencia de escape a un carácter especial, use la sintaxis %\<xx>, donde \<xx> representa el valor hexadecimal ASCII del carácter. Para obtener más información, vea [Cómo: Usar caracteres de escape especiales en MSBuild](../msbuild/how-to-escape-special-characters-in-msbuild.md).

## <a name="special-characters"></a>Caracteres especiales

 En la tabla siguiente se muestran los caracteres especiales de MSBuild:

|**Carácter**|**ASCII**|**Uso reservado**|
|-------------------|---------------|------------------------|
|%|%25|Referencia a metadatos|
|$|%24|Referencia a propiedades|
|@|%40|Referencia a listas de elementos|
|'|%27|Condiciones y otras expresiones|
|;|%3B|Separador de lista|
|?|%3F|Carácter comodín para nombres de archivo en atributos `Include` y `Exclude`|
|*|%2A|Carácter comodín para nombres de archivo en atributos `Include` y `Exclude`|

## <a name="see-also"></a>Vea también

- [Conceptos avanzados](../msbuild/msbuild-advanced-concepts.md)
- [Elementos](../msbuild/msbuild-items.md)
