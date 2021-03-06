---
title: Evaluación de una expresión XPath durante la depuración
ms.date: 03/05/2019
ms.topic: how-to
ms.assetid: 159ba4ef-75e4-4ac8-80dc-e064e0bec345
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 64113461cd081eb97e2eb927119f1cd67f8a8d6e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "85816259"
---
# <a name="evaluate-xpath-expressions"></a>Evaluación de expresiones XPath

Puede evaluar las expresiones XPath mediante la ventana **Inspección rápida** durante la depuración. La expresión XPath debe ser válida de acuerdo con la recomendación XPath 1.0 de W3C. El contexto de XSLT actual (es decir, el nodo `self::node()` de la ventana **Locales**), proporciona el contexto de evaluación para la expresión XPath.

Al evaluar una expresión XPath:

- Se admiten funciones XPath integradas.

- No se admiten funciones XSLT integradas ni funciones definidas por el usuario.

> [!NOTE]
> La depuración XSLT solo está disponible en la edición Enterprise de Visual Studio.

## <a name="evaluate-an-xpath-expression"></a>Evaluación de una expresión XPath

En el siguiente procedimiento se utilizan los archivos *below-average.xsl* y *books.xml* y de la página [Tutorial: Depuración de una hoja de estilos XSLT](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md#sample-files).

1. Inserte un punto de interrupción en la etiqueta de apertura `xsl:if`.

2. Para iniciar la depuración, elija **XML** > **Iniciar depuración de XSLT** en la barra de menús (o presione **Alt**+**F5**).

   Se inicia el depurador y se interrumpe en la etiqueta `xsl:if`.

3. Haga clic con el botón derecho y seleccione **Inspección rápida**.

   La ventana **Inspección rápida** se abre.

4. Escriba `./price/text()` en el campo **Expresión** del cuadro de diálogo **Inspección rápida** y haga clic en **Actualizar**.

   El precio del nodo de libro actual aparece en el cuadro **Valor**.

   ![Evaluación de una expresión XPath en la ventana Inspección rápida](media/quickwatch-price.png)

5. Cambie la expresión XPath a `./price/text() < $bookAverage` y haga clic en **Actualizar**.

   El cuadro **Valor** muestra que la expresión XPath se evalúa como `true`.

## <a name="see-also"></a>Vea también

- [Depuración de XSLT](../xml-tools/debugging-xslt.md)
