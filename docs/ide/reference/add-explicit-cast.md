---
title: Agregar conversión explícita
ms.date: 03/26/2020
ms.topic: reference
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: e159082266b848ce4742e436c706f3f71b2cc9ea
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "84182981"
---
# <a name="add-explicit-cast"></a>Agregar conversión explícita

Esta generación de código se aplica a:

- C#

**Qué:** permite agregar automáticamente una conversión explícita a una expresión, en función del uso.

**Cuándo:** necesita agregar una conversión explícita a una expresión y quiere asignarla correctamente de forma automática.

**Por qué:** podría agregar manualmente una conversión explícita a una expresión, pero esta característica la agrega automáticamente según el contexto del código.

## <a name="how-to-use-it"></a>Cómo se usa

1. Coloque el símbolo de intercalación en el error.
2. Presione **Ctrl**+ **.** para activar el menú **Acciones rápidas y refactorizaciones**.
3. Seleccione **Add explicit cast** (Agregar conversión explícita).

   ![Acción rápida Agregar conversión explícita en Visual Studio](media/add-explicit-cast.png)

## <a name="see-also"></a>Vea también

- [Generación de código](../code-generation-in-visual-studio.md)
- [Refactorización](../refactoring-in-visual-studio.md)
