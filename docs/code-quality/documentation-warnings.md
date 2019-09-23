---
title: Advertencias de documentación
ms.date: 09/16/2019
ms.topic: reference
f1_keywords:
- vs.codeanalysis.documentationrules
helpviewer_keywords:
- documentation warnings
- managed code analysis warnings, documentation warnings
- warnings, documentation
author: mavasani
ms.author: mavasani
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 00b42dc20b228e30a9b2632a0525a1ec8a9ddbb1
ms.sourcegitcommit: 541a0556958201ad6626bc8638406ad02640f764
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2019
ms.locfileid: "71079205"
---
# <a name="documentation-warnings"></a>Advertencias de documentación

Las advertencias de documentación permiten escribir bibliotecas bien documentadas mediante el uso correcto de [comentarios de documentación XML](https://docs.microsoft.com/dotnet/csharp/codedoc) para API visibles externamente.

## <a name="in-this-section"></a>En esta sección

| Regla | DESCRIPCIÓN |
| - | - |
| [CA1200: Evitar el uso de etiquetas CREF con un prefijo](../code-quality/ca1200.md) | El atributo [CREF](https://docs.microsoft.com/dotnet/csharp/programming-guide/xmldoc/cref-attribute) de una etiqueta de documentación XML significa "referencia de código". Especifica que el texto interno de la etiqueta es un elemento de código, como un tipo, un método o una propiedad. Evite el `cref` uso de etiquetas con prefijos, ya que impide que el compilador Compruebe las referencias. También impide que el entorno de desarrollo integrado (IDE) de Visual Studio busque y actualice estas referencias de símbolos durante las refactorizaciones. |

## <a name="see-also"></a>Vea también

- [Advertencias de análisis de código](../code-quality/code-analysis-for-managed-code-warnings.md)