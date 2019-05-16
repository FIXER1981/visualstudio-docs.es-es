---
title: 'CA1410: Métodos de registro COM se deben asociar | Documentos de Microsoft'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
helpviewer_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
ms.assetid: f3b2e62d-fd66-4093-9f0c-dba01ad995fd
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: dd47aa57d128ec5f88f77036546476128aae39f5
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65692071"
---
# <a name="ca1410-com-registration-methods-should-be-matched"></a>CA1410: Los métodos de registro COM deben coincidir
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ComRegistrationMethodsShouldBeMatched|
|Identificador de comprobación|CA1410|
|Categoría|Microsoft.Interoperability|
|Cambio problemático|Poco problemático|

## <a name="cause"></a>Motivo
 Un tipo declara un método marcado con el <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> atributo pero no declara un método marcado con el <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> atributo, o viceversa.

## <a name="rule-description"></a>Descripción de la regla
 Para los clientes del modelo de objetos componentes (COM) crear un [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] tipo, el tipo debe registrarse primero. Si está disponible, un método marcado con el <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> atributo se denomina durante el proceso de registro para ejecutar el código especificado por el usuario. Un método correspondiente que está marcado con el <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute> atributo se denomina durante el proceso de anulación del registro para revertir las operaciones del método de registro.

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones
 Para corregir una infracción de esta regla, agregue el método de anulación del registro o el registro correspondiente.

## <a name="when-to-suppress-warnings"></a>Cuándo suprimir advertencias
 No suprima las advertencias de esta regla.

## <a name="example"></a>Ejemplo
 El ejemplo siguiente muestra un tipo que infringe la regla. El código comentado muestra la corrección de la infracción.

 [!code-csharp[FxCop.Interoperability.ComRegistration#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.ComRegistration/cs/FxCop.Interoperability.ComRegistration.cs#1)]
 [!code-vb[FxCop.Interoperability.ComRegistration#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.ComRegistration/vb/FxCop.Interoperability.ComRegistration.vb#1)]

## <a name="related-rules"></a>Reglas relacionadas
 [CA1411: Métodos de registro COM no deben ser visibles](../code-quality/ca1411-com-registration-methods-should-not-be-visible.md)

## <a name="see-also"></a>Vea también
 <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName> [Registrar ensamblados con COM](https://msdn.microsoft.com/library/87925795-a3ae-4833-b138-125413478551) [Regasm.exe (herramienta de registro de ensamblados)](https://msdn.microsoft.com/library/e190e342-36ef-4651-a0b4-0e8c2c0281cb)
