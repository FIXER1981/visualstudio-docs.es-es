---
title: Sintaxis de ruta de acceso de dominio | Documentos de Microsoft
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, domain path
ms.assetid: 945994f9-72b9-42e0-81b2-e5fb3d0e282d
caps.latest.revision: 27
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 2c115e8fff6cddbc1b08c697b72c7bda3a970ed4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "58999495"
---
# <a name="domain-path-syntax"></a>Sintaxis de las rutas de dominio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Las definiciones de DSL usan una sintaxis del estilo de XPath para ubicar elementos específicos en un modelo.  
  
 Normalmente no tiene que trabajar con esta sintaxis directamente. Cuando aparece en las ventanas DSL Details (Detalles de DSL) o Properties (Propiedades), puede hacer clic en la flecha hacia abajo y usar el editor de rutas. Sin embargo, la ruta aparece con este formato en el campo después de haber usado el editor.  
  
 Una ruta de dominio adopta el formato siguiente:  
  
 *RelationshipName.PropertyName/!Role*  
  
 ![Relación de referencia CommentReferencesSubjects](../modeling/media/dsl-reference.png "dsl_reference")  
  
 La sintaxis atraviesa el árbol del modelo. Por ejemplo, la relación de dominio **CommentReferencesSubjects** en la ilustración anterior tiene un **asuntos** rol. El segmento de ruta de acceso **/! Subjectt** especifica que la ruta de acceso termina en los elementos que se tiene acceso a través del **asuntos** rol.  
  
 Cada segmento comienza con el nombre de una relación de dominio. Si el recorrido es de un elemento a una relación, el segmento de ruta aparece como *relación.NombrePropiedad*. Si el salto es de un vínculo a un elemento, el segmento de ruta aparece como *relación /! RoleName*.  
  
 La sintaxis de una ruta se separa con barras inclinadas. Cada segmento de ruta es un salto desde un elemento a un vínculo (una instancia de una relación) o desde un vínculo a un elemento. Los segmentos de ruta suelen aparecer en parejas. Un segmento de ruta representa un salto desde un elemento a un vínculo, y el siguiente representa un salto desde el vínculo al elemento del otro extremo. (Un vínculo puede ser también origen o destino de una relación).  
  
 El nombre que use para el salto elemento-vínculo es el valor de `Property Name` del rol. El nombre que use para el salto vínculo-elemento es el nombre del rol de destino.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a los modelos, las clases y las relaciones](../modeling/understanding-models-classes-and-relationships.md)
