---
title: Contexto de evaluación de expresiones | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- expression evaluation, context
ms.assetid: a2fd3758-09bd-45ae-8ecc-2d276c0036ba
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e939a4fa5f4673e2f701206c96599c54bc0c3b51
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80738739"
---
# <a name="expression-evaluation-context"></a>Contexto de evaluación de expresiones
En la [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] depuración, un **contexto de evaluación de expresión**:

- Representa un contexto para la evaluación de expresiones. Normalmente, un contexto de evaluación se corresponde con el ámbito léxico en el que se evalúan las variables, los parámetros, las funciones y los métodos. Por ejemplo, un contexto de evaluación de expresión asociado a un marco de pila proporcionará el contexto para evaluar las variables locales, los parámetros de método y los miembros de clase (si procede).

- Existe cuando se detiene un programa en un punto de interrupción. La propia expresión es una estructura de datos que representa una expresión analizada preparada para el enlace y evaluación dentro del contexto especificado.

     Con más detalle, las expresiones se crean mediante el método [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) . Cuando se evalúa una expresión, genera una cadena imprimible que contiene el nombre y el tipo de variable o argumento y su valor. Esta cadena se muestra en el ventana Inspección o en la ventana variables locales del IDE.

     Dado un `BSTR` y una interfaz [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) , un motor de depuración (de) puede crear una interfaz [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) mediante el análisis de una expresión. Dada una `IDebugExpression2` interfaz, el de puede obtener un valor a través de la evaluación de expresiones sincrónicas o asincrónicas. Este valor, junto con el nombre y el tipo de la variable o argumento, se envía al IDE para su presentación.

## <a name="see-also"></a>Vea también
- [Interfaces de evaluación de expresiones](../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [Contextos del depurador](../../extensibility/debugger/debugger-contexts.md)
