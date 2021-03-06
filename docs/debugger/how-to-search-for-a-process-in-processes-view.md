---
title: Búsqueda de un proceso en la vista Procesos | Microsoft Docs
ms.date: 11/04/2016
ms.topic: how-to
helpviewer_keywords:
- Processes view
- processes, searching for
ms.assetid: 7cb97b37-4a95-4f1b-9eee-4910aa9c115b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3b94a052f7cb50df676140b45a43f49b92283903
ms.sourcegitcommit: 062615c058d2ff44751e8d0c704ccfa3c5543469
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90852001"
---
# <a name="how-to-search-for-a-process-in-processes-view"></a>Procedimiento Búsqueda de un proceso en la vista Procesos
Para buscar un proceso específico en la vista Procesos, utilice su id. de proceso o cadena de módulo como criterios de búsqueda. También puede especificar la dirección inicial de la búsqueda. En los campos del cuadro de diálogo se mostrarán los atributos del proceso seleccionado en el árbol de procesos.

### <a name="to-search-for-a-process-in-processes-view"></a>Para buscar un proceso en la vista Procesos

1. Organice las ventanas para que se vean la ventana de Spy++ y una ventana activa de la [vista Procesos](../debugger/processes-view.md).

2. En el menú **Buscar**, seleccione **Buscar proceso**.

    Se abrirá el cuadro de diálogo [Buscar proceso](../debugger/process-search-dialog-box.md).

3. Escriba el id. de proceso o una cadena de módulo como criterios de búsqueda.

4. Borre los campos en los que no quiera especificar ningún valor.

   > [!TIP]
   > Para buscar todos los procesos que pertenecen a un módulo, desactive la casilla **Proceso** y escriba el nombre del módulo en el cuadro **Módulo**. A continuación, use **Buscar siguiente** para seguir buscando procesos.

5. Seleccione **Arriba** o **Abajo** para determinar la dirección inicial de la búsqueda.

6. Haga clic en **Aceptar**.

   Si se encuentra un proceso coincidente, se resaltará en la ventana **vista Procesos**.