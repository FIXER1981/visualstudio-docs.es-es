---
title: Implementación de una clase abstracta
ms.date: 01/26/2018
ms.topic: reference
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 3f8d61e6e2632d62d7244ec0918e56816c3a028e
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2019
ms.locfileid: "72662478"
---
# <a name="implement-an-abstract-class-in-visual-studio"></a>Implementación de una clase abstracta en Visual Studio

Esta generación de código se aplica a:

- C#

- Visual Basic

**Qué:** Permite generar inmediatamente el código necesario para implementar una clase abstracta.

**Cuándo:** Se quiere heredar de una clase abstracta.

**Por qué:** Se podrían implementar manualmente todos los miembros abstractos uno por uno, pero esta característica generará todas las firmas de método de manera automática.

## <a name="how-to"></a>Procedimiento

1. Coloque el cursor en la línea donde hay un subrayado ondulado de color rojo, que señala que ha heredado de una clase abstracta, pero que no ha implementado todos los miembros requeridos.

   - C#:

       ![Código resaltado (C#)](media/abstract-highlight-cs.png)

   - Visual Basic:

       ![Código resaltado (VB)](media/abstract-highlight-vb.png)

2. A continuación, realice alguno de los siguientes procedimientos:

   - **Teclado**
      - Presione **Ctrl**+ **.** para activar el menú **Acciones rápidas y refactorizaciones**.
   - **Mouse**
      - Haga clic con el botón derecho y seleccione el menú **Acciones rápidas y refactorizaciones**.
      - Mantenga el mouse sobre el subrayado ondulado de color rojo y haga clic en el botón ![bombilla de error](media/error-bulb.png) que aparece.
      - Haga clic en el botón ![bombilla de error](media/error-bulb.png) que aparece en el margen izquierdo si el cursor de texto ya está en la línea con el subrayado ondulado de color rojo.

   ![Vista previa de la implementación de la clase](media/abstract-preview-cs.png)

3. Seleccione **Implementar clase abstracta** en el menú desplegable.

   > [!TIP]
   > - Use el vínculo **Vista previa de los cambios** en la parte inferior de la ventana de vista previa [para ver todos los cambios ](../../ide/preview-changes.md) que se aplicarán antes de realizar la selección.
   > - Use los vínculos **Documento**, **Proyecto** y **Solución** de la parte inferior de la ventana de vista previa para crear las firmas de método adecuadas entre las múltiples clases que heredan de la clase abstracta.

   Las firmas de método abstracto se crean y están listas para su implementación.

   - C#:

       ![Resultado de la implementación de la clase (C#)](media/abstract-result-cs.png)

   - Visual Basic:

       ![Resultado de la implementación de la clase (VB)](media/abstract-result-vb.png)

## <a name="see-also"></a>Vea también

- [Generación de código](../code-generation-in-visual-studio.md)
- [Vista previa de cambios](../../ide/preview-changes.md)