---
title: Adición de una regla de umbral para pruebas de carga
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, monitoring
- load tests, thresholds
- load tests, analyzing
- thresholds in load tests
ms.assetid: 3d8fac8f-426f-4155-9ced-f7cd4c79792c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d1389df0c307ad6ec65575fc7934e622928a0ca1
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/01/2020
ms.locfileid: "75591637"
---
# <a name="how-to-add-a-threshold-rule-using-the-load-test-editor"></a>Procedimiento para agregar una regla de umbral mediante el Editor de pruebas de carga

Las reglas de umbral de las pruebas de carga comparan un valor de contador de rendimiento con un valor constante o con otro valor de contador de rendimiento.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="to-add-a-threshold-rule"></a>Para agregar una regla de umbral

1. Abra una prueba de carga.

2. En el Editor de pruebas de carga, expanda el nodo **Conjuntos de contadores**.

3. Expanda una de las **Categorías de contador** en uno de los Conjuntos de contadores. Por ejemplo, puede seleccionar **LoadTest:Scenario**. Expanda el nodo.

4. Haga clic con el botón derecho en uno de los contadores, por ejemplo, **Carga de usuarios**, bajo **LoadTest:Scenario**. Seleccione **Agregar regla de umbral**.

     Se mostrará el cuadro de diálogo **Agregar regla de umbral**.

5. Puede elegir entre dos tipos de reglas: **Comparar constante** y **Compare contador**. Seleccione el tipo adecuado y establezca los valores.

    > [!NOTE]
    > Establezca la propiedad **Alertar si se supera** en **True** para indicar que exceder un umbral supone un problema, o en **False** para indicar que no alcanzar un umbral supone un problema.

## <a name="see-also"></a>Vea también

- [Analizar las infracciones de las reglas de umbral](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [Especificar los conjuntos de contadores y las reglas de umbral para equipos en una prueba de carga](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Analizar los resultados de pruebas de carga](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
