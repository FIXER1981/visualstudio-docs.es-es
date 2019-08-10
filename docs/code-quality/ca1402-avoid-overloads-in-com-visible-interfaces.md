---
title: 'CA1402: Evitar las sobrecargas en interfaces visibles a través de COM'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AvoidOverloadsInComVisibleInterfaces
- CA1402
helpviewer_keywords:
- AvoidOverloadsInComVisibleInterfaces
- CA1402
ms.assetid: 2724c1f9-d5d3-4704-b124-21c4d398e5df
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: aa45a54a994d19b1a04bc0785f21b88dfeef4475
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922126"
---
# <a name="ca1402-avoid-overloads-in-com-visible-interfaces"></a>CA1402: Evitar las sobrecargas en interfaces visibles a través de COM

|||
|-|-|
|TypeName|AvoidOverloadsInComVisibleInterfaces|
|Identificador de comprobación|CA1402|
|Categoría|Microsoft.Interoperability|
|Cambio problemático|Problemático|

## <a name="cause"></a>Causa
Una interfaz visible del modelo de objetos componentes (COM) declara métodos sobrecargados.

## <a name="rule-description"></a>Descripción de la regla
Cuando se exponen métodos sobrecargados a los clientes COM, sólo la primera sobrecarga de método conserva su nombre. Las sobrecargas posteriores se cambian de nombre de forma única anexando al nombre un carácter de subrayado "_" y un entero que se corresponda con el orden de declaración de la sobrecarga. Por ejemplo, considere los siguientes métodos:

```csharp
void SomeMethod(int valueOne);
void SomeMethod(int valueOne, int valueTwo, int valueThree);
void SomeMethod(int valueOne, int valueTwo);
```

Estos métodos se exponen a los clientes COM como se muestra a continuación.

```csharp
void SomeMethod(int valueOne);
void SomeMethod_2(int valueOne, int valueTwo, int valueThree);
void SomeMethod_3(int valueOne, int valueTwo);
```

Visual Basic 6 los clientes COM no pueden implementar métodos de interfaz mediante el uso de un carácter de subrayado en el nombre.

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones
Para corregir una infracción de esta regla, cambie el nombre de los métodos sobrecargados para que los nombres sean únicos. También puede hacer que la interfaz sea invisible para com cambiando la accesibilidad a `internal` (`Friend` en [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) o aplicando el <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> atributo establecido en `false`.

## <a name="when-to-suppress-warnings"></a>Cuándo suprimir advertencias
No suprima las advertencias de esta regla.

## <a name="example"></a>Ejemplo
En el ejemplo siguiente se muestra una interfaz que infringe la regla y una interfaz que cumple la regla.

[!code-vb[FxCop.Interoperability.OverloadsInterface#1](../code-quality/codesnippet/VisualBasic/ca1402-avoid-overloads-in-com-visible-interfaces_1.vb)]
[!code-csharp[FxCop.Interoperability.OverloadsInterface#1](../code-quality/codesnippet/CSharp/ca1402-avoid-overloads-in-com-visible-interfaces_1.cs)]

## <a name="related-rules"></a>Reglas relacionadas
[CA1413: Evitar campos no públicos en tipos de valor visibles para COM](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

[CA1407: Evitar miembros estáticos en tipos visibles para COM](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

[CA1017: Marcar ensamblados con ComVisibleAttribute](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>Vea también

- [Interoperating with Unmanaged Code](/dotnet/framework/interop/index) (Interoperar con código no administrado)
- [Long (tipo de datos)](/dotnet/visual-basic/language-reference/data-types/long-data-type)