---
title: Cómo notificar un problema con Visual Studio 2015 | Microsoft Docs
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.topic: conceptual
ms.assetid: 24ecb76e-b7ad-432d-88ab-d9849963465d
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e75215d2693b5fe2bf879c4b293ae853b42905e7
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2019
ms.locfileid: "72651785"
---
# <a name="how-to-report-a-problem-with-visual-studio-2015"></a>Cómo notificar un problema con Visual Studio 2015
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Para obtener la documentación más reciente de Visual Studio, consulte [Cómo notificar un problema con Visual Studio](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

Si se produce un problema con Visual Studio 2015, queremos saberlo para poder diagnosticarlo y corregirlo.  Mediante el uso de la herramienta **Notificar un problema** , puede recopilar información detallada acerca del problema y enviarla a Microsoft con unos pocos clics de botón.

Microsoft respeta su privacidad. Para obtener información sobre cómo se tratan los datos que nos envía, vea la [Declaración de privacidad de la familia de productos de Microsoft Visual Studio](https://www.visualstudio.com/dn948229).

## <a name="open-the-report-a-problem-tool"></a>Abrir la herramienta Notificar un problema

Haga clic en el icono de comentarios del usuario junto a **Inicio rápido** en la barra de título o bien haga clic en **Ayuda | Enviar comentarios | Notificar un problema**.

![Informe de un problema de elemento de menú](../ide/media/report-a-problem-menu-item.png "Informe de un problema de elemento de menú")

## <a name="describe-the-problem"></a>Describir el problema

### <a name="describe_the_problem"></a>

1. Asigne un título descriptivo al problema que nos ayude a dirigirlo al equipo de Visual Studio correcto.

2. Proporcione detalles adicionales y, si es posible, los pasos para reproducir el problema.

3. Elija un área problemática en la lista desplegable. Seleccione la mejor aproximación si no está seguro.

   ![Informe de un problema de cuadro de diálogo](../ide/media/report-a-problem-dialog.png "Informe de un problema de cuadro de diálogo")

## <a name="provide-a-screenshot-optional"></a>Proporcione una captura de pantalla (opcional)

Elija **Incluir captura de pantalla** para enviar la pantalla actual a Microsoft. La herramienta le permite recortar la imagen para mostrar solo la parte de la pantalla que muestra el problema. Puede adjuntar capturas de pantalla adicionales u otros archivos. Para ello, haga clic en el botón **Adjuntar archivos adicionales** .

## <a name="provide-a-trace-and-heap-dump-optional"></a>Proporcione un volcado de seguimiento y montón (opcional)

### <a name="provide_a_trace_and_heap_dump"></a>

1. Los archivos de volcado de seguimiento y montón son muy útiles para ayudarnos a diagnosticar problemas.   Apreciamos mucho que use la herramienta Notificar un problema para grabar los pasos de reproducción y enviar los datos a Microsoft.

2. Haga clic en el botón de contenido adicional junto a **Registre sus acciones para reproducir el problema**. Si el problema provoca que Visual Studio se bloquee, abra otra instancia de Visual Studio y selecciónela en la Vista de lista.

3. Haga clic en **Iniciar grabación** y realice los pasos que reproducen el problema. Cuando haya terminado, haga clic en **Detener grabación** en la ventana flotante.

4. Espere unos minutos mientras Visual Studio recopila y empaqueta la información que se haya grabado. El cuadro de diálogo tendrá un aspecto similar al siguiente cuando el proceso de recopilación se haya completado:

     ![Registro de un archivo de seguimiento](../ide/media/record-a-trace-file.png "Registro de un archivo de seguimiento")

## <a name="describe-the-workaround-if-there-is-one"></a>Describir la solución alternativa, si la hay

Si pudo solucionar el problema, describa la solución alternativa en el cuadro de edición proporcionado para ese fin. Esto nos ayuda no sólo a diagnosticar el problema, sino también a ayudar a otros usuarios que puedan encontrarse con el mismo problema.

## <a name="submit-the-report"></a>Enviar el informe

Haga clic en el botón Enviar para enviar el informe junto con todas las imágenes y archivos de volcado o de seguimiento. Si el botón **Enviar** está atenuado, asegúrese de que ha proporcionado un título y una descripción.

## <a name="see-also"></a>Otras referencias

- [Hable con nosotros](../ide/talk-to-us.md)
