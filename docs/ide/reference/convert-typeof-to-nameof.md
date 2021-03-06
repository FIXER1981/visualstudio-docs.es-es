---
title: Conversión de typeof en nameof
ms.date: 08/12/2020
ms.topic: reference
author: m-redding
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 233393114883c2a9833aa7ec82f0d78f0ef33bae
ms.sourcegitcommit: 577c905de52057a741e68c2ed168ea527813fda5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2020
ms.locfileid: "88251353"
---
# <a name="convert-typeof-to-nameof"></a>Convertir `typeof` en `nameof`

Esta refactorización se aplica a lo siguiente:

- C#
- Visual Basic

**Qué:** Permite convertir una instancia de `typeof(<QualifiedType>).Name` en `nameof(<QualifiedType>)` en C# y una instancia de `GetType(<QualifiedType>).Name` en `NameOf(<QualifiedType>)` en Visual Basic.

**Cuándo:**  Todas las instancias de `typeof(<QualifiedType>).Name` donde `someType` no es un tipo genérico. Esta exclusión es necesaria porque este caso no devuelve el mismo valor de cadena que `nameof(<QualifiedType>)`. Lo mismo se aplica a la instancia de Visual Basic.

**Por qué:** Al usar `nameof` en lugar del nombre de `type`, se evita la reflexión implicada en la recuperación de un objeto `type`, y es una forma más pragmática de escribirlo.

## <a name="how-to"></a>Instrucciones

1. Coloque el cursor dentro de la instancia de `typeof(<QualifiedType>).Name` para C# o `GetType(<QualifiedType>).Name` en Visual Basic.
2. Presione **Ctrl**+ **.** para activar el menú **Acciones rápidas y refactorizaciones**.
3. Seleccione una de las opciones siguientes:

- C#
  <br>Seleccione **Convertir 'typeof' en 'nameof'** 
  ![ Convertir typeof en nameof](media/convert-type-of.PNG)

- Visual Basic
  <br>Seleccione **Convertir 'GetType' en 'NameOf'** ![ Convertir typeof en nameof](media/convert-get-type.PNG)

## <a name="see-also"></a>Vea también

- [Refactorización](../refactoring-in-visual-studio.md)
