---
title: Diseñador de actividad Diseñador de flujo de trabajo-Sequence
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Sequence.UI
ms.assetid: 51c8d3cb-4d43-458f-9631-b63755f9ac94
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 77980077a580724f6db6bb5a544200890421d8e5
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "86875974"
---
# <a name="sequence-activity-designer"></a>Diseñador actividades Sequence

La actividad <xref:System.Activities.Statements.Sequence> contiene una colección ordenada de actividades secundarias que ejecuta por orden.

Otra manera de ejecutar un conjunto de actividades por orden es utilizar una actividad <xref:System.Activities.Statements.Flowchart>. Considere la posibilidad de usar el [Diagrama de flujo](../workflow-designer/flowchart-activity-designer.md) cuando tenga un flujo simple de bifurcación o de bucles que desee modelar diagrama.

## <a name="using-the-sequence-activity-designer"></a>Utilizar el diseñador de actividades Sequence

Para agregar una <xref:System.Activities.Statements.Sequence> actividad, arrastre el diseñador de actividad **Sequence** desde el **cuadro de herramientas** y colóquelo en la superficie diseñador de flujo de trabajo. Para agregar una actividad secundaria a esta <xref:System.Activities.Statements.Sequence> actividad, arrastre otra actividad del cuadro de **herramientas** y colóquela sobre el triángulo en el cuadro que contiene el texto de la sugerencia "Coloque la actividad aquí".

### <a name="sequence-activity-properties-in-the-workflow-designer"></a>Propiedades de la actividad Sequence en el Diseñador de flujo de trabajo

En la tabla siguiente se muestran las propiedades <xref:System.Activities.Statements.Sequence> y se describe cómo se utilizan en el diseñador. Estas propiedades se pueden editar en la cuadrícula de propiedades o en la superficie del diseñador.

|Nombre de propiedad|Obligatorio|Uso|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|Falso|Especifica el nombre descriptivo del diseñador de actividades <xref:System.Activities.Statements.Sequence> en el encabezado. El valor predeterminado es Sequence. El valor se puede editar en la cuadrícula de propiedades o directamente en el encabezado del diseñador de actividades.<br /><br /> Aunque el valor de la propiedad <xref:System.Activities.Activity.DisplayName%2A> no sea obligatorio, el procedimiento recomendado es usar uno.|

## <a name="see-also"></a>Consulte también

- [Diagrama de flujo](../workflow-designer/flowchart-activity-designer.md)
- [Flujo de control](../workflow-designer/control-flow-activity-designers.md)