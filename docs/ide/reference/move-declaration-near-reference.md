---
title: Acercamiento de la declaración de variable a la referencia
ms.date: 01/26/2018
ms.topic: reference
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 35735009a5b813ca29159f276fe2d5abb734be0e
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/01/2020
ms.locfileid: "75585289"
---
# <a name="move-declaration-near-reference-refactoring"></a>Refactorización de acercamiento de la declaración a la referencia

Esta refactorización se aplica a lo siguiente:

- C#

**Qué:** Permite acercar las declaraciones de variable a su uso.

**Cuándo:** Hay declaraciones de variable que pueden estar en un ámbito más restringido.

**Por qué:** Se podría dejar tal cual, pero podría causar problemas de legibilidad u ocultar información. Se trata de una oportunidad de refactorización para mejorar la legibilidad.

## <a name="how-to"></a>Procedimiento

1. Coloque el cursor en la declaración de variable.

1. A continuación, realice alguno de los siguientes procedimientos:

   - **Teclado**
      - Presione **Ctrl**+ **.** para activar el menú **Acciones rápidas y refactorizaciones** y seleccione **Mover la declaración cerca de la referencia** en el menú emergente de la ventana Vista previa.
   - **Mouse**
      - Haga clic con el botón derecho en el código, seleccione el menú **Acciones rápidas y refactorizaciones** y elija **Mover la declaración cerca de la referencia** en el menú emergente de la ventana Vista previa.

1. Cuando esté satisfecho con el cambio, presione **Entrar** o haga clic en la solución en el menú y los cambios se confirmarán.

Ejemplo:

```csharp
// Before
int x;
if (condition)
{
    x = 1;
    Console.WriteLine(x);
}

// Move declaration near reference

// After
if (condition)
{
    int x = 1;
    Console.WriteLine(x);
}
```

## <a name="see-also"></a>Vea también

- [Refactorización](../refactoring-in-visual-studio.md)
- [Vista previa de cambios](../../ide/preview-changes.md)
