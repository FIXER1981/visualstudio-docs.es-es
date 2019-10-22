---
title: Explorador de esquemas XML | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 2fc39e98-b194-456b-a452-cfafb0a52d66
caps.latest.revision: 11
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 5e9f61c56dd7ff2a9c6c19afc20ed279a7fdf855
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2019
ms.locfileid: "72669371"
---
# <a name="xml-schema-explorer"></a>Explorador de esquemas XML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

El Explorador de esquemas XML está integrado en Microsoft Visual Studio y en el Editor XML para permitirle trabajar con los esquemas del lenguaje de definición de esquema XML (XSD). Al abrir un archivo de esquema XML, el nodo **conjunto de esquemas** aparece en el explorador de esquemas XML. También aparecerán en el Explorador de esquemas XML todos los esquemas incluidos, importados o redefinidos para el archivo de destino, así como los archivos a los que se hace referencia mediante una instrucción `include` o `import`.

 El Explorador de esquema XML permite hacer lo siguiente:

- Obtener información general rápida del conjunto de esquemas.

- Examinar y desplazarse por el árbol.

- Realizar búsquedas específicas del esquema y de palabras clave. Para obtener más información, vea [Buscar en el conjunto de esquemas](../xml-tools/searching-the-schema-set.md).

- Agregar los resultados de la búsqueda a la vista Gráfico o Modelo de contenido

- Ordenar el árbol por documento, tipo o nombre. Para obtener más información, vea [ordenar, filtrar y agrupar](../xml-tools/sorting-filtering-and-grouping-xml-schema-explorer.md).

- Abrir el Editor XML y saltar a las ubicaciones de código del archivo XSD. Para obtener más información, vea [integración con el editor XML](../xml-tools/integration-with-xml-editor.md).

- Generar XML de ejemplo para elementos globales.

  El Explorador de esquema XML proporciona una vista jerárquica del conjunto de esquemas mediante una vista de árbol. El Explorador de esquema XML también proporciona búsqueda, filtrado, navegación y ordenación. Para tener acceso al Explorador de esquemas XML, realice una de las operaciones siguientes:

- Si está en la [vista Inicio](../xml-tools/start-view.md), haga clic en el vínculo **Explorador de esquemas XML** .

- Si está en la [vista gráfico](../xml-tools/graph-view.md) o en la [vista modelo de contenido](../xml-tools/content-model-view.md) y tiene nodos en el área de trabajo, use el menú contextual para seleccionar el explorador de esquemas XML.

- También puede seleccionar el esquema XML Explorerfrom el menú **Ver** .

- Puede tener acceso al esquema XML Explorerfrom un archivo. VB que tiene un literal XML Visual Basic asociado a un archivo. xsd. Para ver el esquema establecido en el explorador de esquemas XML, haga clic con el botón secundario en un nodo XML de un literal XML o una importación de espacio de nombres XML y seleccione el comando **Mostrar en el explorador de esquemas** . Para obtener más información, vea [integración de literales XML con el explorador de esquemas XML](../xml-tools/integration-of-xml-literals-with-xml-schema-explorer.md).

## <a name="tree-view"></a>Vista de árbol
 El Explorador de esquema XML muestra la información de conjunto de esquemas precompilada en una estructura de árbol. La estructura de árbol está organizada de la forma siguiente:

- En la parte superior está el nodo del conjunto de esquemas.

- El segundo nivel contiene los espacios de nombres.

- El tercer nivel contiene los archivos.

- El cuarto nivel contiene los nodos globales. Esto puede incluir elementos, grupos, tipos complejos, tipos simples, atributos, grupos de atributos e instrucciones `include`, `import` y `redefine`.

  A continuación se muestra un ejemplo de estructura de árbol:

  ![Explorador de esquemas XML](../xml-tools/media/xmlschemaexplorer.gif "XMLSchemaExplorer")

## <a name="selection-and-activation"></a>Selección y activación
 Para resaltar y seleccionar un nodo, haga clic una vez en el Explorador de esquemas.

 Para activar un nodo, haga doble clic en él o presione **entrar** cuando se seleccione el nodo.

- Al activar un nodo, se abre el archivo en el que está definido (si no está abierto ya) y se selecciona el nodo en dicho archivo.

- Al activar un nodo de archivo, se abre el archivo seleccionado (si no está abierto ya) y se resalta el nodo del `<schema>`.

- Al activar un nodo de espacio de nombres o de conjunto de esquemas no se realiza ninguna acción.

## <a name="draging-and-dropping-nodes"></a>Arrastrar y colocar nodos
 Puede arrastrar y colocar nodos globales, de archivo y de espacio de nombres en una vista del Diseñador XSD. Si la vista actual es la [vista Inicio](../xml-tools/start-view.md), al arrastrar un nodo a la vista se abrirá la [vista gráfico](../xml-tools/graph-view.md). Si la vista actual es la vista de [modelo de contenido](../xml-tools/content-model-view.md) o la vista de gráfico, la vista no cambiará cuando coloque un nodo en ella.

 Al quitar archivos de la vista, se agregarán todos los nodos globales del archivo al [área de trabajo del diseñador XSD](../xml-tools/xml-schema-designer-workspace.md). Al colocar los espacios de nombres en la vista, se agregarán al área de trabajo todos los nodos globales del espacio de nombres. El área de trabajo la comparten todas las vistas.

 No es posible arrastrar y colocar nodos locales ni importaciones.

## <a name="in-this-section"></a>En esta sección

- [Buscar en el conjunto de esquemas](../xml-tools/searching-the-schema-set.md)

- [Ordenación, filtrado y agrupación](../xml-tools/sorting-filtering-and-grouping-xml-schema-explorer.md)

- [Menús contextuales](../xml-tools/context-menus-xml-schema-explorer.md)

- [Integración de los literales XML con el Explorador de esquemas XML](../xml-tools/integration-of-xml-literals-with-xml-schema-explorer.md)

## <a name="see-also"></a>Vea también
 [Cómo: Agregar nodos al área de trabajo desde el Explorador de esquemas XML](../xml-tools/how-to-add-nodes-to-the-workspace-from-the-xml-schema-explorer.md)
