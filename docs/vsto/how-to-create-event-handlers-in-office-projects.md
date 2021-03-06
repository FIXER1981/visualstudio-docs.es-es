---
title: 'Cómo: crear controladores de eventos en proyectos de Office'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visual Basic [Office development in Visual Studio], event handlers
- event handlers [Office development in Visual Studio]
- Visual C# [Office development in Visual Studio], event handlers
- events [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ee85d89dcb990cebd595dadbd7b28add4a7b371a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "85538312"
---
# <a name="how-to-create-event-handlers-in-office-projects"></a>Cómo: crear controladores de eventos en proyectos de Office
  Hay varias maneras de crear controladores de eventos en Visual Basic y C#. En la vista Diseño, puede crear los controladores de eventos predeterminados para los controles haciendo doble clic en el control, o bien usar el panel eventos de la ventana **propiedades** para crear controladores para cualquier evento del control. Sin embargo, si está en la vista de código, es posible que no desee cambiar a Vista de diseño para crear un controlador de eventos.

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

### <a name="to-create-an-event-handler-in-visual-basic"></a>Para crear un controlador de eventos en Visual Basic

1. En la lista desplegable **nombre de clase** de la parte superior del editor de código, seleccione el objeto para el que desea crear un controlador de eventos.

    > [!NOTE]
    > Si desea crear controladores de eventos para `ThisDocument` o `ThisWorkbook` , debe seleccionar **(eventos ThisDocument)** o **(eventos ThisWorkbook)** en la lista desplegable **nombre de clase** .

2. En la lista desplegable **nombre de método** de la parte superior del editor de código, seleccione el evento.

     Visual Studio crea el controlador de eventos y mueve el punto de inserción al controlador de eventos recién creado. Si el controlador de eventos ya existe, el punto de inserción se desplaza al controlador de eventos existente.

### <a name="to-create-an-event-handler-in-c"></a>Para crear un controlador de eventos en C\#

1. Cree el delegado de eventos en el evento **Startup** de la clase escribiendo el nombre de evento completo seguido de un espacio y escribiendo **+=** sin espacio después. Por ejemplo:

     `this.<object name>.<event name> +=`

2. Al final de la línea de código, presione la tecla TAB dos veces.

     Visual Studio completa automáticamente la línea de código, crea el controlador de eventos y mueve el punto de inserción al controlador de eventos recién creado.

## <a name="see-also"></a>Consulte también
- [Escribir código en soluciones de Office](../vsto/writing-code-in-office-solutions.md)
- [Tutorial: programar contra eventos de un control NamedRange](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)
- [Compilar soluciones de Office](../vsto/building-office-solutions.md)
