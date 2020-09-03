---
title: 'Cómo: Crear un sombreador Lambert básico | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: ec5c10fb-9600-4240-8280-d59451ea1d68
caps.latest.revision: 22
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 038b3e7db7f1e3b79ee3e41b6e256216a39b91bd
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "72664558"
---
# <a name="how-to-create-a-basic-lambert-shader"></a>Cómo: Crear un sombreador Lambert básico
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

En este documento se muestra cómo usar el Diseñador de sombras y el lenguaje DGSL (Directed Graph Shader Language) para crear un sombreador de iluminación que implementa el modelo de iluminación de Lambert clásico.

 Este documento muestra estas actividades:

- Agregar nodos a un gráfico de sombreador

- Desconectar nodos

- Conectar nodos

## <a name="the-lambert-lighting-model"></a>El modelo de iluminación de Lambert
 El modelo de iluminación de Lambert incorpora iluminación ambiental y direccional para sombrear objetos en una escena 3D. Los componentes ambientales proporcionan un nivel de iluminación base en la escena 3D. Los componentes direccionales proporcionan iluminación adicional de fuentes de luz direccionales (lejanas). La iluminación ambiental afecta a todas las superficies de la escena igualmente, sin importar su orientación. Para una superficie determinada, es el producto del color de ambiente de la superficie y del color y la intensidad de la luz ambiental en la escena. La iluminación direccional afecta a cada superficie de la escena de manera diferente, en función de la orientación de la superficie con respecto a la dirección de la fuente de luz. Es un producto del color difuso y la orientación de la superficie, y del color, la intensidad y la dirección de las fuentes de luz. Las superficies que miran directamente hacia la fuente de luz reciben la máxima contribución y las superficies que miran directamente al otro lado no reciben ninguna contribución. Bajo el modelo de iluminación de Lambert, se combinan el componente ambiental y uno o más componentes direccionales para determinar la contribución de color difuso total para cada punto del objeto.

 Antes de empezar, asegúrese de que se muestran la ventana **Propiedades** y el **Cuadro de herramientas**.

#### <a name="to-create-a-lambert-shader"></a>Para crear un sombreador Lambert básico

1. Cree un sombreador DGSL con el que trabajar. Para obtener información sobre cómo agregar un sombreador DGSL al proyecto, vea la sección Introducción de [Diseñador de sombras](../designers/shader-designer.md).

2. Desconecte el nodo **Color de punto** del nodo **Color final**. Elija el terminal **RGB** del nodo **Color de punto** y, después, elija **Romper vínculos**. Deje el terminal **Alfa** conectado.

3. Agregue un nodo **Lambert** al gráfico. En el **Cuadro de herramientas**, en **Utilidad**, seleccione **Lambert** y muévalo a la superficie de diseño. El nodo Lambert calcula la contribución de color difuso total del píxel, en función de parámetros de iluminación ambiente y difusa.

4. Conecte el nodo **Color de punto** al nodo **Lambert**. En modo **Seleccionar**, mueva el terminal **RGB** del nodo **Color de punto** al terminal **Color difuso** del nodo **Lambert**. Esta conexión proporciona al nodo Lambert el color difuso interpolado del píxel.

5. Conecte el valor de color calculado al color final. Mueva el terminal **Salida** del nodo **Lambert** al terminal **RGB** del nodo **Color final**.

   La ilustración siguiente muestra el gráfico de sombreador completo y una vista previa del sombreador aplicado a un modelo de tetera.

> [!NOTE]
> Para demostrar mejor el efecto del sombreador en esta ilustración, se especificó un color naranja mediante el parámetro **MaterialDiffuse** del sombreador. Un juego o una aplicación puede usar este parámetro para proporcionar un valor de color único para cada objeto. Para obtener información sobre los parámetros de materiales, vea la sección Vista previa de sombreadores en [Diseñador de sombras](../designers/shader-designer.md).

 ![Gráfico de sombreador y vista previa de su efecto.](../designers/media/digit-lambert-effect-graph.png "Digit-Lambert-Effect-Graph")

 Es posible que algunas formas proporcionen mejores vistas previas para algunos sombreadores. Para obtener más información sobre cómo obtener una vista previa de los sombreadores en el diseñador de sombras, vea la sección vista previa de sombreadores en el [Diseñador de sombras](../designers/shader-designer.md).

 La siguiente ilustración muestra el sombreador descrito en este documento aplicado a un modelo 3D.

 ![Iluminación Lambert aplicada a un modelo.](../designers/media/digit-lambert-effect-result.png "Digit-Lambert-Effect-result")

 Para más información sobre cómo aplicar un sombreador a un modelo 3D, vea [Cómo: Aplicar un sombreador a un modelo 3D](../designers/how-to-apply-a-shader-to-a-3-d-model.md).

## <a name="see-also"></a>Consulte también
 [Cómo: aplicar un sombreador a un modelo 3D](../designers/how-to-apply-a-shader-to-a-3-d-model.md) [Cómo: exportar un sombreador](../designers/how-to-export-a-shader.md) [Cómo: crear un](../designers/how-to-create-a-basic-phong-shader.md) diseñador [de sombras de](../designers/shader-designer.md) Phong básico nodos del [Diseñador](../designers/shader-designer-nodes.md) de sombras de sombreador
