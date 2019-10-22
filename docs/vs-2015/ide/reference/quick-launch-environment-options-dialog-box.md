---
title: Inicio rápido, Entorno, Opciones (cuadro de diálogo) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Environment.QuickLaunch
- vs.quicklaunch
helpviewer_keywords:
- searching IDE
- IDE, searching
ms.assetid: 4200f297-d065-4723-9a30-d91ff2e26c9d
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 77220ef55871d59bf8c8810547fccae5399869ce
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2019
ms.locfileid: "72665678"
---
# <a name="quick-launch-environment-options-dialog-box"></a>Inicio rápido, Entorno, Opciones (cuadro de diálogo)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Puede usar **Inicio rápido** para buscar y ejecutar acciones rápidamente para los activos IDE como opciones, plantillas y menús. No puede usar **Inicio rápido** para buscar símbolos y código. El cuadro de búsqueda **Inicio rápido** está situado en la esquina superior derecha de la barra de menús y es accesible mediante las teclas Ctrl+Q. Simplemente escriba la cadena de búsqueda en el cuadro. Para buscar cadenas que contengan @, use «@@».

 **Inicio rápido** está habilitado de forma predeterminada al instalar Visual Studio. En la barra de menús, puede mostrar u ocultar **Inicio rápido** mediante **Herramientas**, **Opciones**. Expanda el nodo **Entornos** y, después, elija **Inicio rápido**. Active o desactive la casilla **Habilitar Inicio rápido**. También puede habilitar o deshabilitar categorías de búsqueda en esta página.

## <a name="category-list"></a>Lista de categorías
 Aparecen los resultados de búsqueda de Inicio rápido en cuatro categorías: **Usados más recientemente**, **Menús**, **Opciones** y **Documentos abiertos**, junto con el número de elementos de la categoría. Para desplazarse por los resultados de búsqueda por categoría, pulse las teclas Ctrl + Q para mostrar todos los resultados de la categoría. Después de que aparezca la última categoría, CTRL + Q le muestra unos pocos resultados de cada categoría. Puede usar Ctrl + Mayús + Q para desplazarse por las categorías en orden inverso. Para ver todos los resultados de búsqueda en una categoría, elija el nombre de la categoría.

 Puede utilizar los siguientes accesos directos para limitar la búsqueda a las categorías específicas.

|Categoría|Acceso directo|Descripción del acceso directo|
|--------------|--------------|--------------------------|
|Usados más recientemente|@mru<br /><br /> Por ejemplo, `@mru font`.|Muestra hasta cinco de los elementos que ha **usado más recientemente**.|
|Menús|@menu<br /><br /> Por ejemplo, `@menu font`.|Limita la búsqueda a los elementos de menú.|
|Opciones|@opt<br /><br /> Por ejemplo, `@opt font`.|Limita la búsqueda a la configuración del cuadro de diálogo **Opciones**.|
|Documentos|@doc<br /><br /> Por ejemplo, `@doc font`.|Limita la búsqueda a los nombres de archivo y rutas de acceso de documentos abiertos para los criterios de búsqueda, pero no busca el texto dentro de los propios archivos.|

> [!NOTE]
> Puede cambiar las teclas de método abreviado en la página **General**, **Teclado**, en el cuadro de diálogo **Opciones**.

## <a name="show-previous-results"></a>Mostrar resultados anteriores
 De forma predeterminada, el término de búsqueda que especifique no se conserva de una sesión de búsqueda a otra. La cadena de búsqueda se borra si busca un término. Mueva el cursor fuera del área de **Inicio rápido** y, después, regrese. Para conservar los resultados de búsqueda, vaya al cuadro de diálogo **Opciones**, seleccione **Inicio rápido** y, después, seleccione la casilla **Mostrar resultados de la búsqueda anterior cuando se active el inicio rápido** . La próxima vez que realice una búsqueda, salga del área de Inicio rápido y retroceda. Inicio rápido conservará el término de búsqueda que se utilizó por última vez y también le mostrará los resultados de búsqueda.

 Para conocer las últimas sugerencias y trucos para usar el **Inicio rápido**, vea el [blog de Visual Studio](http://go.microsoft.com/fwlink/?LinkId=236054).

## <a name="see-also"></a>Vea también
 [Elementos generales de la interfaz de usuario (Visual Studio)](../../ide/reference/general-user-interface-elements-visual-studio.md) [cuadro de diálogo Opciones de entorno](../../ide/reference/environment-options-dialog-box.md)
