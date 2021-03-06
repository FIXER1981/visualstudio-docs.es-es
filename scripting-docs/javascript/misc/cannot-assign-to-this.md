---
title: No se puede asignar a ' this ' | Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: error-reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5000
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ba2b0a2b-f0f8-4698-b335-a4ab6c166671
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8985c7201a8e315353dd89ab5e1f5a3ad3b403ea
ms.sourcegitcommit: e38419bb842d587fd9e37c24b6cf3fc5c2e74817
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "91862769"
---
# <a name="cannot-assign-to-this"></a>No se puede asignar a 'this'
Ha intentado asignar un valor a **este**. **esta** es una [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] palabra clave que hace referencia a:

- objeto que ejecuta actualmente un método.

- objeto global si no hay ningún método actual (o el método no pertenece a ningún otro objeto).

Un método es una [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] función que se invoca a través de un objeto. Dentro de un método, la palabra clave **this** es una referencia al objeto al que se invocó el método (que es el objeto creado mediante la invocación del constructor de clase con el operador **New** ).

Dentro de un método, se puede **utilizar para hacer referencia al objeto** actual, pero no se puede asignar un nuevo valor a **este**.

## <a name="to-correct-this-error"></a>Para corregir este error

- No intente asignar a **este**. Para tener acceso a una propiedad o un método de un objeto con instancias, utilice el operador de punto (por ejemplo, **Circle. RADIUS**).

  > [!NOTE]
  > No se puede asignar un nombre a una variable creada por **el**usuario; es una [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] palabra reservada.

## <a name="see-also"></a>Vea también

- [Esta instrucción](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Operators/this)
- [Solución de problemas de los scripts](https://developer.mozilla.org/docs/Learn/JavaScript/First_steps/What_went_wrong)