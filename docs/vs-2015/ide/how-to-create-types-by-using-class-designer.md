---
title: 'Cómo: Crear tipos con el Diseñador de clases | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.Clr.ClrAttributesDialog
helpviewer_keywords:
- custom attributes, applying
- class diagrams, creating types
- classes [Visual Studio], creating with Class Designer
- Class Designer [Visual Studio], creating classes
- types [Visual Studio], class diagrams
- attributes [Visual Studio], applying custom
ms.assetid: 94458c31-28bc-40e2-9737-85868788a0e5
caps.latest.revision: 45
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d05b8a492768dfe9163d7ede55c2bf4aef084c26
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2019
ms.locfileid: "72668026"
---
# <a name="how-to-create-types-by-using-class-designer"></a>Cómo: Crear tipos con el Diseñador de clases
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Para diseñar nuevos tipos para proyectos de Visual C# .NET y Visual Basic .NET, créelos en un diagrama de clases. Para ver los tipos existentes, vea [Cómo: Ver los tipos existentes (Diseñador de clases)](../ide/how-to-view-existing-types-class-designer.md).

- [Crear un tipo nuevo](#CreateType)

- [Aplicar un atributo personalizado a un tipo](#CustAttributeType)

- [Aplicar un atributo personalizado a un miembro de tipo](#CustAttributeMember)

## <a name="CreateType"></a> Crear un tipo nuevo

1. En el cuadro de herramientas, en Diseñador de clases, arrastre uno de estos a un diagrama de clase:

    - **Clase** o **Clase abstracta**

    - **Enum**

    - **Interface**

    - **Estructura** (VB) o **Struct** (C#)

    - **Delegate**

    - **Módulo** (solo en VB)

2. Escriba un nombre para el tipo. Después seleccione su nivel de acceso.

3. Seleccione el archivo donde desea agregar el código inicial para el tipo:

    - Para crear un archivo nuevo y agregarlo al proyecto actual, seleccione **Crear nuevo archivo** y escriba un nombre de archivo.

    - Para agregar código a un archivo existente, seleccione **Agregar al archivo existente**.

         Si la solución tiene un proyecto que comparte código en varias aplicaciones, puede agregar un nuevo tipo a un diagrama de clases del proyecto de la aplicación, pero solo si el archivo de clases correspondiente está en el mismo proyecto de la aplicación o en el proyecto compartido.

4. Ahora agregue otros elementos para definir el tipo:

    |||
    |-|-|
    |**For**|**Add**|
    |Clases, clases abstractas, estructuras o structs|Métodos, propiedades, campos, eventos, constructores (método), destructores (método) y constantes que definen el tipo|
    |Enumeraciones|Valores de campo que constituyen la enumeración|
    |Interfaces|Métodos, propiedades y eventos que constituyen la interfaz|
    |delegado|Parámetros que definen el delegado|
    |Module|Métodos, propiedades, campos, eventos, constructores (método) y constantes que definen el módulo|

     Vea [Crear miembros](../ide/creating-and-configuring-type-members-class-designer.md#CreateMembers).

## <a name="CustAttributeType"></a> Aplicar un atributo personalizado a un tipo

1. Haga clic en la forma del tipo en un diagrama de clases.

2. En la ventana Propiedades, junto a la propiedad **Atributos personalizados** del tipo, haga clic en el botón de puntos suspensivos (...).

3. Agregue uno o varios atributos personalizados, uno por línea. No los encierre entre corchetes.

     Cuando haya acabado, los atributos personalizados se aplicarán al tipo.

## <a name="CustAttributeMember"></a> Aplicar un atributo personalizado a un miembro de tipo

1. Haga clic en el nombre del miembro, en la forma del tipo en un diagrama de clases o en la fila en la ventana Detalles de clase.

2. En la ventana Propiedades, busque la propiedad **Atributos personalizados** del miembro.

3. Agregue uno o varios atributos personalizados, uno por línea. No los encierre entre corchetes.

     Cuando haya acabado, los atributos personalizados se aplicarán al tipo.

## <a name="see-also"></a>Vea también
 [Cómo: crear la herencia entre tipos (diseñador de clases)](../ide/how-to-create-inheritance-between-types-class-designer.md) [Cómo: crear asociaciones entre tipos (diseñador de clases)](../ide/how-to-create-associations-between-types-class-designer.md) [crear y configurar miembros de tipo (diseñador de clases)](../ide/creating-and-configuring-type-members-class-designer.md) [trabajar con diagramas de clases (diseñador de clases)](../ide/working-with-class-diagrams-class-designer.md) [Diseñar clases y tipos (diseñador de clases)](../ide/designing-classes-and-types-class-designer.md)
