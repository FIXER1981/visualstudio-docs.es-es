---
title: 'Paso 7: Agregar problemas de multiplicación y división'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: e638959e-f6a4-4eb4-b2e9-f63b7855cf8f
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6bc9c1e28b86956c611d48d332c3444665a66de4
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55917823"
---
# <a name="step-7-add-multiplication-and-division-problems"></a>Paso 7: Agregar problemas de multiplicación y división
En la séptima parte de este tutorial, agregará los problemas de multiplicación y división, pero primero piense en cómo realizar ese cambio. Piense en el paso inicial, que requiere almacenar valores.

## <a name="to-add-multiplication-and-division-problems"></a>Para agregar problemas de multiplicación y división

1.  Agregue cuatro variables de entero más al formulario.

     [!code-vb[VbExpressTutorial3Step7#15](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_1.vb)]
     [!code-csharp[VbExpressTutorial3Step7#15](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_1.cs)]

2.  Tal como hizo antes, modifique el método `StartTheQuiz()` para rellenar los problemas de multiplicación y división con números aleatorios.

     [!code-vb[VbExpressTutorial3Step7#16](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_2.vb)]
     [!code-csharp[VbExpressTutorial3Step7#16](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_2.cs)]

3.  Modifique el método `CheckTheAnswer()` para que también compruebe los problemas de multiplicación y división.

     [!code-vb[VbExpressTutorial3Step7#17](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_3.vb)]
     [!code-csharp[VbExpressTutorial3Step7#17](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_3.cs)]

     Dado que no resulta fácil escribir el signo de multiplicación (×) y el signo de división (÷) mediante el teclado, Visual C# y Visual Basic aceptan el asterisco (*) para la multiplicación y la barra diagonal (/) para la división.

4.  Cambie la última parte del controlador de evento <xref:System.Windows.Forms.Timer.Tick> del temporizador para que rellene la respuesta correcta cuando se agote el tiempo.

     [!code-vb[VbExpressTutorial3Step7#23](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_4.vb)]
     [!code-csharp[VbExpressTutorial3Step7#23](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_4.cs)]

5.  Guarde y ejecute el programa.

     Los jugadores deben responder a cuatro problemas para completarla, como se muestra en la ilustración siguiente.

     ![Prueba matemática con cuatro problemas](../ide/media/express_finishedquiz.png)
**Math quiz** with four problems

## <a name="to-continue-or-review"></a>Para continuar o revisar

-   Para ir al siguiente paso del tutorial, vea [Paso 8: Personalizar la prueba](../ide/step-8-customize-the-quiz.md).

-   Para volver al paso anterior del tutorial, vea [Paso 6: Agregar un problema de resta](../ide/step-6-add-a-subtraction-problem.md).
