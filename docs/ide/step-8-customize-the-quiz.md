---
title: 'Paso 8: Personalizar la prueba'
ms.date: 11/04/2016
ms.topic: tutorial
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
dev_langs:
- CSharp
- VB
ms.assetid: dc8edb13-1b23-47d7-b859-8c6f7888c1a9
author: ornellaalt
ms.author: ornella
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e568a9fa844802ddab934264cbc316d3514fe577
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2020
ms.locfileid: "77579370"
---
# <a name="step-8-customize-the-quiz"></a>Paso 8: Personalizar la prueba

En la última parte del tutorial, explorará algunas maneras de personalizar la prueba y ampliar sus conocimientos. Por ejemplo, piense en cómo el programa crea problemas de división aleatorios para los que la respuesta nunca es una fracción. Para obtener más información, cambie el color del control `timeLabel` y proporcione al usuario alguna sugerencia.

> [!NOTE]
> Este tema forma parte de una serie de tutoriales sobre conceptos de codificación básicos. Para obtener información general sobre el tutorial, vea [Tutorial 2: Crear una prueba matemática cronometrada](../ide/tutorial-2-create-a-timed-math-quiz.md).

## <a name="to-customize-the-quiz"></a>Para personalizar la prueba

- Cuando solo queden cinco segundos en un cuestionario, cambie el color del control **timeLabel** a rojo al establecer su propiedad **BackColor**.

  ```csharp
  timeLabel.BackColor = Color.Red;
  ```

  ```vb
  timeLabel.BackColor = Color.Red
  ```

  [!INCLUDE [devlang-control-csharp-vb](./includes/devlang-control-csharp-vb.md)]

  Restablezca el color cuando la prueba haya terminado.

- Proporcione una sugerencia al jugador reproduciendo un sonido cuando especifique una respuesta correcta en un control <xref:System.Windows.Forms.NumericUpDown>. (Tendrá que escribir un controlador de eventos para el evento <xref:System.Windows.Forms.NumericUpDown.ValueChanged> de cada control, que se desencadena cada vez que el jugador cambia el valor del control.)

## <a name="to-continue-or-review"></a>Para continuar o revisar

- Para ir al tutorial siguiente, consulte **[Tutorial 3: Crear un juego de formar parejas](../ide/tutorial-3-create-a-matching-game.md)** .

- Para volver al paso anterior del tutorial, vea [Paso 7: Agregar problemas de multiplicación y división](../ide/step-7-add-multiplication-and-division-problems.md).
