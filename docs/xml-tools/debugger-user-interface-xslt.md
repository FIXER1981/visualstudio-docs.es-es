---
title: Ventanas del depurador XSLT
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 846fdabd-e5c3-4688-9b0d-a93fbeea1b96
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b25c47e6db79fe4b860b6e7c209f0fc8403d0fcd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62838498"
---
# <a name="debugger-user-interface-xslt"></a>Interfaz de usuario del depurador (XSLT)

En este artículo se describe los cuadros de diálogo y ventanas del depurador. Solo se explican las partes de la interfaz de usuario que tienen un comportamiento de depuración específico de XSLT.

Para obtener más información, consulte el [depuración: referencia de la interfaz de usuario](../debugger/debugging-user-interface-reference.md).

## <a name="locals-window"></a>Ventana Locales

La ventana Locales muestra información acerca de las variables definidas en la hoja de estilos. Contiene tres columnas de información:

**Name**

Esta columna contiene los nombres de todas las variables locales del ámbito actual. Los conjuntos de nodos tienen un control de árbol que puede explorar en profundidad para ver sus subcarpetas.

**Valor**

Esta columna muestra el valor que contiene cada variable. Los nodos de atributo, instrucción de procesamiento, comentario, texto y CData muestran el valor de texto del nodo. Los nodos de espacio de nombres muestran el URI del espacio de nombres.

**Tipo**

Esta columna identifica el tipo de datos de cada variable mostrada en el **nombre** columna.

La ventana Locales muestra también las variables de contexto predefinidas que realizan el seguimiento del contexto de la transformación XSLT. En la tabla siguiente se describen las variables de contexto predefinidas que emplea el depurador de XSLT.

|Name|Descripción|
|-|-----------------|
|`last()`|El tamaño del contexto.|
|`position()`|La posición, o número de índice, del nodo de contexto, con respecto al tamaño del contexto.|
|`self::node()`|El valor del nodo de contexto.|

## <a name="output-window"></a>Resultados (ventana)

La Ventana de salida muestra los mensajes de error o las excepciones de seguridad que se producen durante la depuración. También muestra la salida del depurador.

## <a name="task-list"></a>Lista de tareas

El **lista de tareas** enumera todos los errores de compilación en la hoja de estilos. Al hacer doble clic en el error, el cursor se desplaza hasta la línea con el error.

El **lista de tareas** incluye todos los errores que se producen en los bloques de script en el archivo XSLT.

> [!NOTE]
> El depurador de XSLT no tiene advertencias, así que nunca aparecerán en la **lista de tareas**.

## <a name="breakpoints-window"></a>ventana Puntos de interrupción

La ventana Puntos de interrupción muestra todos los puntos de interrupción definidos en el proyecto actual. Si se agrega un punto de interrupción mientras la ventana está a la vista, ésta se actualiza automáticamente para mostrar el nuevo punto de interrupción.

La ventana Puntos de interrupción debe tener el mismo comportamiento que otros depuradores de Visual Studio.

## <a name="watch-window"></a>Ventana Inspección

La ventana Inspección se utiliza para evaluar variables. y cambiar sus valores.

Las variables que se muestran en esta ventana guardan relación con el contexto actual (el elemento superior de la pila de llamadas). Si cambia el contexto, la ventana Inspección se actualiza y muestra las variables definidas para ese contexto.

## <a name="call-stack-window"></a>Ventana Pila de llamadas

El **pila de llamadas** ventana sirve para ver los nombres de funciones en la pila de llamadas, tipos de parámetros y valores de parámetro. La información de la pila de llamadas solo se muestra cuando el programa que se está depurando se encuentra en estado de interrupción.

La pila de llamadas representa los diversos contextos por los que atraviesa la ejecución XSLT. Por ejemplo, si hay una llamada de plantilla "a" a la plantilla "b", la plantilla "a" y la plantilla "b" aparece en la **pila de llamadas** ventana con el contexto actual en la parte superior de la lista. El usuario puede ver la consulta actualmente en ejecución.

Si las plantillas no tienen un nombre en el archivo XSLT, se utilizan los nombres generados por el procesador XSLT.

Al hacer clic en otro elemento que no es el que se encuentra en primer lugar de la lista se indica al visor dónde ha tenido lugar la rama de la ejecución XSLT mediante el uso de resaltes y flechas verdes estándar.

## <a name="quickwatch-dialog-box"></a>Inspección rápida (cuadro de diálogo)

El **Inspección rápida** cuadro de diálogo se usa para evaluar expresiones XPath 1.0. El nodo de contexto (el nodo `self::node()` de la ventana Locales) proporciona el contexto para la ejecución de la expresión XPath. El resultado de la ejecución de la expresión XPath se muestra en la ventana Inspección.

La siguiente lista describe las restricciones en la evaluación de expresiones XPath:

- Solo se permiten funciones XPath integradas.

- Funciones XSLT integradas como `document()` y `key()` no se permiten.

- No se permiten funciones definidas por el usuario.

Para obtener más información, vea [Cómo: Evaluar una expresión XPath](../xml-tools/how-to-evaluate-an-xpath-expression.md).

## <a name="disassembly-window"></a>ventana Desensamblado

La ventana Desensamblado muestra el código ensamblador generado por el compilador de XSLT. Esta ventana se puede utilizar de la misma manera que todas las demás ventanas de desensamblado de Visual Studio.

Para obtener más información, [Cómo: Utilice la ventana Desensamblado](../debugger/how-to-use-the-disassembly-window.md).

## <a name="see-also"></a>Vea también

- [Depuración de XSLT](../xml-tools/debugging-xslt.md)
- [Primer vistazo al depurador](../debugger/debugger-feature-tour.md)
- [Inspeccionar las variables en las ventanas automático y variables locales de Visual Studio](../debugger/autos-and-locals-windows.md)