---
title: Enumeraciones de Visual C++ en el Diseñador de clases
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Class Designer [Visual Studio], enumerations
ms.assetid: 11e90ba1-18cd-44f8-9e26-e3746a7a19d1
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: f31f153183d0cdd809bd9dde9187ade32b20ddd2
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55939858"
---
# <a name="visual-c-enumerations-in-class-designer"></a>Enumeraciones de Visual C++ en el Diseñador de clases

El **Diseñador de clases** admite tipos `enum` y `enum class` de ámbito de C++. A continuación se muestra un ejemplo:

```cpp
enum CardSuit {
   Diamonds = 1,
   Hearts = 2,
   Clubs = 3,
   Spades = 4
};

// or...
enum class CardSuit {
   Diamonds = 1,
   Hearts = 2,
   Clubs = 3,
   Spades = 4
};
```

Una forma de enumeración de C++ en un diagrama de clases se parece y funciona como una forma de estructura, salvo que en la etiqueta se muestra **Enum** o **Enum class**, es de color fucsia en lugar de azul y el borde de los márgenes superior e izquierdo está coloreado. Tanto las formas de enumeración como las formas de estructura tienen las esquinas cuadradas.

Para obtener más información sobre cómo usar el tipo `enum`, vea [Enumerations (Enumeraciones)](/cpp/cpp/enumerations-cpp).

## <a name="see-also"></a>Vea también

- [Trabajar con código de Visual C++](working-with-visual-cpp-code.md)
- [Enumeraciones](/cpp/cpp/enumerations-cpp)