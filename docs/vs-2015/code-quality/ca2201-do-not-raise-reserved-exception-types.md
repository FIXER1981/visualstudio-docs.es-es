---
title: 'CA2201: no generar tipos de excepción reservados | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotRaiseReservedExceptionTypes
- CA2201
helpviewer_keywords:
- CA2201
- DoNotRaiseReservedExceptionTypes
ms.assetid: dd14ef5c-80e6-41a5-834e-eba8e2eae75e
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 9533a597a33deaed17ff2a73d56ef306ea7b5613
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "85546346"
---
# <a name="ca2201-do-not-raise-reserved-exception-types"></a>CA2201: No provocar tipos de excepción reservados
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Elemento|Value|
|-|-|
|TypeName|DoNotRaiseReservedExceptionTypes|
|Identificador de comprobación|CA2201|
|Category|Microsoft. Usage|
|Cambio problemático|Problemático|

## <a name="cause"></a>Causa
 Un método produce un tipo de excepción que es demasiado general o que está reservado por el motor en tiempo de ejecución.

## <a name="rule-description"></a>Descripción de la regla
 Los siguientes tipos de excepción son demasiado generales para proporcionar información suficiente al usuario:

- <xref:System.Exception?displayProperty=fullName>

- <xref:System.ApplicationException?displayProperty=fullName>

- <xref:System.SystemException?displayProperty=fullName>

  Los siguientes tipos de excepción están reservados y solo los puede iniciar el Common Language Runtime:

- <xref:System.ExecutionEngineException?displayProperty=fullName>

- <xref:System.IndexOutOfRangeException?displayProperty=fullName>

- <xref:System.NullReferenceException?displayProperty=fullName>

- <xref:System.OutOfMemoryException?displayProperty=fullName>

  **No producir excepciones generales**

  Si se produce un tipo de excepción general, como <xref:System.Exception> o <xref:System.SystemException> en una biblioteca o un marco de trabajo, obliga a los consumidores a detectar todas las excepciones, incluidas las excepciones desconocidas que no saben cómo controlar.

  En su lugar, inicie un tipo más derivado que ya exista en el marco de trabajo, o cree su propio tipo que deriva de <xref:System.Exception> .

  **Producir excepciones específicas**

  En la tabla siguiente se muestran los parámetros y las excepciones que se producen al validar el parámetro, incluido el parámetro de valor en el descriptor de acceso set de una propiedad:

|Descripción del parámetro|Excepción|
|---------------------------|---------------|
|`null` referencia|<xref:System.ArgumentNullException?displayProperty=fullName>|
|Fuera del intervalo permitido de valores (por ejemplo, un índice para una colección o lista)|<xref:System.ArgumentOutOfRangeException?displayProperty=fullName>|
|Valor no válido `enum`|<xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=fullName>|
|Contiene un formato que no cumple las especificaciones de los parámetros de un método (como la cadena de formato para `ToString(String)` )|<xref:System.FormatException?displayProperty=fullName>|
|De lo contrario|<xref:System.ArgumentException?displayProperty=fullName>|

 Cuando una operación no es válida para el estado actual de un objeto Throw <xref:System.InvalidOperationException?displayProperty=fullName>

 Cuando se realiza una operación en un objeto que se ha eliminado Throw <xref:System.ObjectDisposedException?displayProperty=fullName>

 Cuando no se admite una operación (por ejemplo, en una secuencia invalidada **. Write** en una secuencia abierta para lectura) throw <xref:System.NotSupportedException?displayProperty=fullName>

 Cuando una conversión produciría un desbordamiento (por ejemplo, en una sobrecarga de operador de conversión explícita) <xref:System.OverflowException?displayProperty=fullName>

 En todas las demás situaciones, considere la posibilidad de crear su propio tipo que se deriva de <xref:System.Exception> y lo lanza.

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones
 Para corregir una infracción de esta regla, cambie el tipo de la excepción iniciada por un tipo específico que no sea uno de los tipos reservados.

## <a name="when-to-suppress-warnings"></a>Cuándo suprimir advertencias
 No suprima las advertencias de esta regla.

## <a name="related-rules"></a>Reglas relacionadas
 [CA1031: No capturar los tipos de excepción general](../code-quality/ca1031-do-not-catch-general-exception-types.md)
