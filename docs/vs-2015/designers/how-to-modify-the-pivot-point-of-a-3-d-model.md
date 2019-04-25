---
title: Procedimiento Modificar el punto de pivote de un modelo 3D | Documentos de Microsoft
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: c20b4ec8-29f5-4ca5-bc39-d4548ca6f573
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f63c271e096793a03616356b9eb7229e4f823fbd
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "60071790"
---
# <a name="how-to-modify-the-pivot-point-of-a-3-d-model"></a>Procedimiento Modificar el punto de pivote de un modelo 3D
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

En este documento se muestra cómo usar el Editor de modelos para modificar el *punto de pivote* de un modelo 3D. El punto de pivote es el punto en el espacio que define el centro matemático del objeto para la rotación y la escala.  
  
 Este documento muestra esta actividad:  
  
- Modificar el punto de pivote de un objeto  
  
## <a name="modifying-the-pivot-point-of-a-3-d-model"></a>Modificar el punto de pivote de un modelo 3D  
 Puede volver a definir el origen de un modelo 3D modificando el punto de pivote.  
  
 Asegúrese de que se muestran la ventana **Propiedades** y el **Cuadro de herramientas**.  
  
#### <a name="to-modify-the-pivot-point-of-a-3-d-model"></a>Para modificar el punto de pivote de un modelo 3D  
  
1. Comience con un modelo 3D existente, como el que se describe en [Cómo: Crear un modelo 3D básico](../designers/how-to-create-a-basic-3-d-model.md).  
  
2. Cambie al modo de pivote. En la barra de herramientas **Modo del Editor de modelos** haga clic en el botón **Modo de pivote** para activar este modo. Aparece un cuadro alrededor del botón **Modo de pivote** para indicar que el Editor de modelos está ahora en modo de pivote. En el modo de pivote, operaciones como la traslación afectan al punto de pivote del objeto en lugar de a la estructura del objeto en el espacio global.  
  
3. Modifique el punto de pivote del objeto. En el modo **Seleccionar**, seleccione el objeto y, después, en la barra de herramientas del **Visor de modelos**, seleccione la herramienta **Trasladar**. Aparecerá un cuadro que representa el punto de pivote en la superficie de diseño. Mueva el cuadro para modificar el punto de pivote del objeto.  
  
    Al mover el cuadro puede mover el punto de pivote en las tres dimensiones. Para trasladar el punto de pivote a lo largo de un eje, mueva la flecha que se corresponde a ese eje. El cuadro y las flechas cambiarán a un color amarillo para indicar el eje que se ve afectado por la traslación.  
  
    También puede especificar el punto de pivote mediante la propiedad **Traslación de punto pivote** en la ventana **Propiedades**.  
  
   > [!TIP]
   >  Puede ver el efecto del nuevo punto de pivote girando el objeto. Para girarlo, use la herramienta **Girar** o modifique la propiedad **Rotación**.  
  
   Este es un modelo que tiene un punto de pivote modificado:  
  
   ![Modelo de una casa que tiene un punto de pivote modificado](../designers/media/digit-modified-model.png "Digit-Modified-Model")  
  
## <a name="see-also"></a>Vea también  
 [Cómo: Crear un modelo 3D básico](../designers/how-to-create-a-basic-3-d-model.md)   
 [Editor de modelos](../designers/model-editor.md)
