---
title: Usar conjuntos de reglas para especificar las reglas de C++ que se van a ejecutar | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
ms.assetid: ac3877e6-5349-4c03-9541-3d5be259f1e8
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: jillfra
ms.openlocfilehash: ff105af1d817613b324e1158130457eb906c753f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "77277856"
---
# <a name="using-rule-sets-to-specify-the-c-rules-to-run"></a>Usar conjuntos de reglas para especificar las reglas C++ que se van a ejecutar
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

En [!INCLUDE[vsPreShort](../includes/vspreshort-md.md)] y [!INCLUDE[vsUltShort](../includes/vsultshort-md.md)] , puede crear y modificar un conjunto de *reglas* personalizado para satisfacer las necesidades específicas del proyecto asociadas con el análisis de código. Para crear un conjunto de reglas personalizado de C++, un proyecto de C/C++ debe estar abierto en el IDE de Visual Studio. A continuación, se abre un conjunto de reglas estándar en el editor de conjuntos de reglas y, a continuación, se agregan o quitan reglas específicas y, opcionalmente, se cambia la acción que se produce cuando el análisis de código determina que se ha infringido una regla.  
  
 Para crear un nuevo conjunto de reglas personalizado, guárdelo con un nuevo nombre de archivo. El conjunto de reglas personalizado se asigna automáticamente al proyecto.  
  
## <a name="opening-the-rule-set-editor"></a>Abrir el editor de conjuntos de reglas  
  
#### <a name="to-create-a-custom-rule-from-a-single-existing-rule-set"></a>Para crear una regla personalizada a partir de un solo conjunto de reglas existente  
  
1. En Explorador de soluciones, abra el menú contextual del proyecto y, a continuación, elija **propiedades**.  
  
2. En la pestaña **propiedades** , elija **análisis de código**.  
  
3. En la lista desplegable **conjunto de reglas** , realice una de las acciones siguientes:  
  
   - Elija el conjunto de reglas que desea personalizar.  
  
     \- o -  
  
   - Elija esta opción **\<Browse...>** para especificar un conjunto de reglas existente que no esté en la lista.  
  
4. Elija **abrir** para mostrar las reglas en el editor de conjuntos de reglas.  
  
#### <a name="to-modify-a-rule-set-in-the-rule-set-editor"></a>Para modificar un conjunto de reglas en el editor de conjuntos de reglas  
  
- Para cambiar el nombre para mostrar del conjunto de reglas, en el menú **Ver** , elija **ventana Propiedades**. Escriba el nombre para mostrar en el cuadro **nombre** . Observe que el nombre para mostrar puede diferir del nombre de archivo.  
  
- Para agregar todas las reglas del grupo a un conjunto de reglas personalizado, active la casilla del grupo. Para quitar todas las reglas del grupo, desactive la casilla.  
  
- Para agregar una regla concreta al conjunto de reglas personalizado, active la casilla de la regla. Para quitar la regla del conjunto de reglas, desactive la casilla.  
  
- Para cambiar la acción realizada cuando se infringe una regla en un análisis de código, elija el campo **acción** de la regla y, a continuación, elija uno de los siguientes valores:  
  
     **WARN** : genera una advertencia.  
  
     **Error** : genera un error.  
  
     **Ninguno** : deshabilita la regla. Esta acción es igual que quitar la regla del conjunto de reglas.  
  
#### <a name="to-group-filter-or-change-the-fields-in-the-rule-set-editor-by-using-the-rule-set-editor-toolbar"></a>Para agrupar, filtrar o cambiar los campos del editor de conjuntos de reglas mediante la barra de herramientas del editor  
  
- Para expandir las reglas de todos los grupos, seleccione **expandir todo**.  
  
- Para contraer las reglas de todos los grupos, elija **contraer todo**.  
  
- Para cambiar el campo por el que se agrupan las reglas, elija el campo en la lista **Agrupar por** . Para mostrar las reglas desagrupadas, elija **\<None>** .  
  
- Para agregar o quitar campos en columnas de regla, elija **Opciones de columna**.  
  
- Para ocultar reglas que no se aplican a la solución actual, elija **Ocultar reglas que no se aplican a la solución actual**.  
  
- Para cambiar entre mostrar y ocultar reglas que tienen asignada la acción error, elija **Mostrar reglas que pueden generar errores de análisis de código**.  
  
- Para cambiar entre mostrar y ocultar reglas que tienen asignada la acción ADVERTENCIA, elija **Mostrar reglas que pueden generar advertencias de análisis de código**.  
  
- Para cambiar entre mostrar y ocultar reglas que tienen asignada la acción **ninguno** , elija **Mostrar reglas que no estén habilitadas**.  
  
- Para agregar o quitar conjuntos de reglas predeterminadas de Microsoft en el conjunto de reglas actual, elija **Agregar o quitar conjuntos de reglas secundarios**.
