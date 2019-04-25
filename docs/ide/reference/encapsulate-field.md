---
title: Refactorización de un campo a una propiedad
ms.date: 01/26/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
f1_keywords:
- vs.csharp.refactoring.encapsulatefield
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 9030fd2ae85d12760d6f6a12be54492f3c14e12b
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55911279"
---
# <a name="encapsulate-a-field-refactoring"></a>Refactorización de encapsulamiento de un campo

Esta refactorización se aplica a lo siguiente:

- C#

- Visual Basic

**Qué:** Permite convertir un campo en una propiedad y actualizar todos los usos de ese campo para usar la propiedad recién creada.

**Cuándo:** Se quiere mover un campo a una propiedad y actualizar todas las referencias a ese campo.

**Por qué:** Se quiere proporcionar acceso a un campo a otras clases, pero no que esas clases tengan acceso directo.  Al encapsular el campo en una propiedad, puede escribir código para comprobar el valor que se está asignando, por ejemplo.

## <a name="how-to"></a>Procedimiento

1. Resalte o coloque el cursor de texto en el nombre del campo que se va a encapsular:

   - C#:

       ![Código resaltado (C#)](media/encapsulate-highlight-cs.png)

   - Visual Basic:

       ![Código resaltado (Visual Basic)](media/encapsulate-highlight-vb.png)

2. A continuación, realice alguno de los siguientes procedimientos:

   - **Teclado**
      - Presione **CTRL+R** y, a continuación, **CTRL+E**.  (Tenga en cuenta que su método abreviado de teclado puede ser diferente en función del perfil que haya seleccionado).
      - Presione **Ctrl**+**.** para activar el menú **Acciones rápidas y refactorizaciones** y seleccione la entrada **Encapsular campo** en el menú emergente de la ventana Vista previa.
   - **Mouse**
      - Seleccione **Editar > Refactorizar > encapsular campo**.
      - Haga clic con el botón derecho en el código, seleccione el menú **Acciones rápidas y refactorizaciones** y elija la entrada **Encapsular campo** en el menú emergente de la ventana Vista previa.

   Selección | Descripción
   --------- | -----------
   **Encapsular campo (y usar propiedad)** | Encapsula el campo con una propiedad y actualiza todos los usos del campo para utilizar la propiedad generada
   **Encapsular campo (pero seguir usando el campo)** | Encapsula el campo con una propiedad, pero deja intactos todos los usos del campo

   La propiedad se crea y se actualizan las referencias al campo, si se han seleccionado.

   > [!TIP]
   > Use el vínculo **Vista previa de los cambios** de la ventana emergente [para ver cuál será el resultado](../../ide/preview-changes.md) antes de confirmar.

   - C#:

      ![Resultado de encapsulamiento de la propiedad (C#)](media/encapsulate-result-cs.png)

   - Visual Basic:

      ![Resultado de encapsulamiento de la propiedad (Visual Basic)](media/encapsulate-result-vb.png)

## <a name="see-also"></a>Vea también

- [Refactorización](../refactoring-in-visual-studio.md)
- [Vista previa de cambios](../../ide/preview-changes.md)