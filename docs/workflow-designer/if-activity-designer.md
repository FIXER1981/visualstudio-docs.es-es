---
title: 'Diseñador de flujo de trabajo: si el Diseñador de actividad'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.If.UI
ms.assetid: 930a8fa2-db98-43e9-ad6d-a85cc7a6519a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 762199906bbb84701c044b5fa9f3f3b8c6fdfdae
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55916978"
---
# <a name="if-activity-designer"></a>Diseñador de actividades If

La actividad <xref:System.Activities.Statements.If> evalúa una condición y ejecuta una actividad según los resultados de esa evaluación. Esta actividad es muy útil cuando se utiliza un estilo de modelado por procedimientos de programación. Una actividad <xref:System.Activities.Statements.If> puede estar anidada en una actividad <xref:System.Activities.Statements.Sequence> o en una actividad <xref:System.Activities.Statements.Parallel>, por ejemplo. Si está utilizando una actividad <xref:System.Activities.Statements.Flowchart>, plantéese utilizar una actividad <xref:System.Activities.Statements.FlowDecision> en su lugar.

## <a name="if-properties-in-the-workflow-designer"></a>Propiedades If en el Diseñador de flujo de trabajo

En la tabla siguiente se muestran las actividades <xref:System.Activities.Statements.If> más útiles y se describe cómo se utilizan en el diseñador.

|Nombre de la propiedad|Obligatorio|Uso|
|-|--------------|-|
|<xref:System.Activities.Statements.If.Condition%2A>|True|La condición que determina qué actividad secundaria se va a ejecutar. Para establecer el <xref:System.Activities.Statements.If.Condition%2A>, escriba una expresión de Visual Basic en el **condición** cuadro en el **si** actividad diseñador o en la cuadrícula de propiedades.|
|<xref:System.Activities.Statements.If.Else%2A>|False|La actividad que se ejecutarán si la <xref:System.Activities.Statements.If.Condition%2A> es **false**. Para agregar una actividad que es ejecutada por el <xref:System.Activities.Statements.If.Else%2A> bifurcar, coloque una actividad de la **cuadro de herramientas** en el **Else** cuadro en el **si** Diseñador de actividad con el texto de la sugerencia " Colocar actividad aquí".|
|<xref:System.Activities.Statements.If.Then%2A>|False|La actividad que se ejecutarán si la <xref:System.Activities.Statements.If.Condition%2A> es **true**. Para agregar una actividad que es ejecutada por el <xref:System.Activities.Statements.If.Then%2A> bifurcar, coloque una actividad de la **cuadro de herramientas** en el **, a continuación,** cuadro en el **si** Diseñador de actividad con el texto de la sugerencia " Colocar actividad aquí".|

## <a name="see-also"></a>Vea también

- [Sequence](../workflow-designer/sequence-activity-designer.md)
- [Parallel](../workflow-designer/parallel-activity-designer.md)
- [Flujo de control](../workflow-designer/control-flow-activity-designers.md)