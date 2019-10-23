---
title: 'Cómo: usar el visualizador de árboles de WPF | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- WPF, debugging
- debugging, WPF
ms.assetid: 2a1bf1cd-90f9-4d06-9fb4-1bfc925afef3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0adcca4acd5fc72d301d707ccdd831c86ef3e48f
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72731924"
---
# <a name="how-to-use-the-wpf-tree-visualizer"></a>Cómo: Usar el visualizador de árboles de WPF
Puede usar el visualizador de árboles de WPF para explorar el árbol visual de un objeto de WPF y ver las propiedades de dependencia de WPF para los objetos contenidos en ese árbol. Para obtener más información sobre los árboles visuales, vea [árboles en WPF](/dotnet/framework/wpf/advanced/trees-in-wpf). Para obtener más información sobre las propiedades de dependencia, consulte [información general sobre las propiedades de dependencia](/dotnet/framework/wpf/advanced/dependency-properties-overview).

 Al abrir el visualizador de árboles de WPF, verá dos paneles: el **árbol visual** a la izquierda y las **propiedades del** panel _nombre_ **:** _tipo_ de la derecha. Seleccione cualquier objeto en el panel del **árbol visual** y las **propiedades del** panel _nombre_ **:** _tipo_ se actualizan automáticamente para mostrar las propiedades de ese objeto.

### <a name="to-open-the-wpf-tree-visualizer"></a>Para abrir el visualizador de árboles de WPF

1. En una Información sobre datos, una ventana **Inspección**, una ventana **Automático** o una ventana **Variables locales**, junto al nombre de un objeto WPF, haga clic en la flecha adyacente al icono de lupa.

     Se mostrará una lista de visualizadores.

2. Haga clic en **Visualizador de árboles de WPF**.

### <a name="to-search-the-visual-tree"></a>Para buscar en el árbol visual

- En el panel **Árbol visual**, escriba la cadena que desea buscar en el cuadro **Buscar**.

  El visualizador de árboles de WPF buscará inmediatamente el primer objeto del árbol visual que coincida con la cadena que ha escrito. Escriba más caracteres si desea buscar una coincidencia más precisa.

  - Para ir a la siguiente coincidencia dentro del árbol visual, haga clic en **Siguiente**.

  - Para volver a la coincidencia anterior, haga clic en **Anterior**.

  - Para borrar el criterio de búsqueda, haga clic en **Borrar**.

### <a name="to-search-the-properties-list"></a>Para buscar en la lista de propiedades

- En el panel **propiedades de** _nombre_ **:** _tipo_ , escriba la cadena que desea buscar en el cuadro de **filtro** .

  El visualizador de árboles de WPF buscará inmediatamente las propiedades que coincidan con la cadena que ha escrito; ahora, la lista solo muestra las propiedades que coinciden con la cadena que ha escrito. Escriba más caracteres si desea buscar una coincidencia más precisa.

  - Para borrar el criterio de búsqueda, haga clic en **Borrar**.

### <a name="to-close-the-visualizer"></a>Para cerrar el visualizador

- Haga clic en el icono **Cerrar** situado en la esquina superior derecha del cuadro de diálogo.

## <a name="see-also"></a>Vea también
- [Create Custom Visualizers](../debugger/create-custom-visualizers-of-data.md) (Crear visualizadores personalizados)
- [Árboles en WPF](/dotnet/framework/wpf/advanced/trees-in-wpf)
- [Información general sobre las propiedades de dependencia](/dotnet/framework/wpf/advanced/dependency-properties-overview)
