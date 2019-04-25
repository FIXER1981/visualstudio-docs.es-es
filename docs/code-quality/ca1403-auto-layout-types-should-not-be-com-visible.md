---
title: 'CA1403: Los tipos de diseño automático no deben ser visibles a través de COM'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AutoLayoutTypesShouldNotBeComVisible
- CA1403
helpviewer_keywords:
- CA1403
- AutoLayoutTypesShouldNotBeComVisible
ms.assetid: a7007714-f9b4-4730-94e0-67d3dc68991f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: fa965caf63dad6e81e2aeabbc93e97c7aa4b7a80
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55910875"
---
# <a name="ca1403-auto-layout-types-should-not-be-com-visible"></a>CA1403: Los tipos de diseño automático no deben ser visibles a través de COM

|||
|-|-|
|TypeName|AutoLayoutTypesShouldNotBeComVisible|
|Identificador de comprobación|CA1403|
|Categoría|Microsoft.Interoperability|
|Cambio problemático|Problemático|

## <a name="cause"></a>Motivo

Un tipo de valor visibles del modelo de objetos componentes (COM) se marca con el <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=fullName> atributo establecido en <xref:System.Runtime.InteropServices.LayoutKind.Auto?displayProperty=fullName>.

## <a name="rule-description"></a>Descripción de la regla

<xref:System.Runtime.InteropServices.LayoutKind> tipos de diseño son administrados por common language runtime. El diseño de estos tipos puede cambiar entre las versiones de .NET Framework, lo que interrumpe a los clientes COM que esperan un diseño concreto. Si el <xref:System.Runtime.InteropServices.StructLayoutAttribute> no se especifica el atributo, especifican los compiladores de C#, Visual Basic y C++ [LayoutKind.Auto](<xref:System.Runtime.InteropServices.LayoutKind.Auto>) para tipos de valor.

A menos que marque en caso contrario, todos los tipos públicos y no genéricos son visibles para COM y todos los tipos no públicos y genéricos no son visibles para COM. Sin embargo, para reducir los falsos positivos, esta regla requiere la visibilidad de COM de tipo explícita. El ensamblado contenedor debe estar marcado con el <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> establecido en `false` y el tipo se debe marcar con el <xref:System.Runtime.InteropServices.ComVisibleAttribute> establecido en `true`.

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones

Para corregir una infracción de esta regla, cambie el valor de la <xref:System.Runtime.InteropServices.StructLayoutAttribute> atributo [LayoutKind.Explicit](<xref:System.Runtime.InteropServices.LayoutKind.Explicit>) o [LayoutKind.Sequential](<xref:System.Runtime.InteropServices.LayoutKind.Sequential>), o hacer que el tipo sea invisible para COM.

## <a name="when-to-suppress-warnings"></a>Cuándo Suprimir advertencias

No suprima las advertencias de esta regla.

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra un tipo que infringe la regla y un tipo que cumple la regla.

[!code-csharp[FxCop.Interoperability.AutoLayout#1](../code-quality/codesnippet/CSharp/ca1403-auto-layout-types-should-not-be-com-visible_1.cs)]
[!code-vb[FxCop.Interoperability.AutoLayout#1](../code-quality/codesnippet/VisualBasic/ca1403-auto-layout-types-should-not-be-com-visible_1.vb)]

## <a name="related-rules"></a>Reglas relacionadas

[CA1408: No utilizar AutoDual ClassInterfaceType](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)

## <a name="see-also"></a>Vea también

- [Calificar tipos de .NET para la interoperación](/dotnet/framework/interop/qualifying-net-types-for-interoperation)
- [Interoperar con código no administrado](/dotnet/framework/interop/index)