---
title: GUID e identificadores de barras de herramientas de Visual Studio | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- visual studio groups
- toolbars
- visual studio toolbar
- id
- toolgar group
- tool window toolbar
- guid
ms.assetid: c9cacd57-9225-450f-a9ac-cbf3168ea844
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fe42821cdacc038d767e52373d45ddd7b8954323
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "80708227"
---
# <a name="guids-and-ids-of-visual-studio-toolbars"></a>GUID e identificadores de barras de herramientas de Visual Studio
En este tema se enumeran los valores de GUID y de identificador de las barras de herramientas que se incluyen en el entorno de desarrollo integrado (IDE) de Visual Studio y de los grupos que contienen. Estos valores se definen en los archivos *. Vsct* que se instalan como parte del SDK de Visual Studio. Para obtener más información, vea [comandos, menús y grupos definidos por el IDE](../../extensibility/internals/ide-defined-commands-menus-and-groups.md).

> [!NOTE]
> Muchas de las barras de herramientas disponibles para Visual Studio no están definidas por Visual Studio, y sus valores GUID y ID no son públicos. En este tema solo se enumeran las barras de herramientas definidas en los archivos *. Vsct* de Visual Studio SDK.

 Para obtener más información sobre cómo trabajar con objetos IDE definidos en archivos *. Vsct* , vea [extender menús y comandos](../../extensibility/extending-menus-and-commands.md).

 Las barras de herramientas predeterminadas que proporciona el IDE de Visual Studio usan el GUID `guidSHLMainMenu` , excepto si, de lo contrario, se especifica mediante la `GUID:ID` Sintaxis.

## <a name="ide-toolbars"></a>Barras de herramientas del IDE
 El IDE de Visual Studio proporciona las siguientes barras de herramientas. Las barras de herramientas se pueden mostrar seleccionándola en el submenú **barras de herramientas** del menú **herramientas** . Las barras de herramientas de las ventanas de herramientas no se incluyen en esta sección.

 Solo los grupos pueden descender directamente de las barras de herramientas. Para agregar un grupo, establezca su elemento primario en el GUID y el identificador de la barra de herramientas. Para agregar un botón a una barra de herramientas, establezca su elemento primario en un grupo en la barra de herramientas.

|Barra de herramientas|ID|
|-------------|--------|
|Estándar|IDM_VS_TOOL_STANDARD|
|Compilar|IDM_VS_TOOL_BUILD|
|Editor de texto|IDM_VS_TOOL_TEXTEDITOR|
|Depurar|guidVSDebugGroup: IDM_DEBUG_TOOLBAR|
|Ubicación de depuración|guidVSDebugGroup: IDM_DEBUG_CONTEXT_TOOLBAR|

### <a name="special-toolbars"></a>Barras de herramientas especiales
 Estas barras de herramientas están definidas por el IDE de Visual Studio, pero sirven funciones especializadas y no hospedan grupos de comandos.

|Barra de herramientas|ID|
|-------------|--------|
|Add (Comando)|IDM_VS_TOOL_ADDCOMMAND|
|No definido|IDM_VS_TOOL_UNDEFINED|
|esquema XML|IDM_VS_TOOL_SCHEMA|
|datos XML|IDM_VS_TOOL_DATA|

## <a name="groups-on-the-ide-toolbars"></a>Grupos en las barras de herramientas del IDE
 Para agregar un botón a una barra de herramientas estándar, establezca uno de los siguientes grupos como su elemento primario. Los grupos se ordenan por la barra de herramientas primaria.

### <a name="standard-toolbar-groups"></a>Grupos de barras de herramientas estándar

|Nombre|ID|
|----------|--------|
|Guardar o abrir|IDG_VS_TOOLSB_SAVEOPEN|
|Cortar o copiar|IDG_VS_TOOLSB_CUTCOPY|
|Deshacer/rehacer|IDG_VS_TOOLSB_UNDOREDO|
|Ejecutar/compilar|IDG_VS_TOOLSB_RUNBUILD|
|Buscar|IDG_VS_TOOLSB_SEARCH|
|Windows|IDG_VS_TOOLSB_WINDOWS|
|Nuevas ventanas|IDG_VS_TOOLSB_NEWWINDOWS|
|Cargar/guardar|IDG_VS_WINDOWUI_LOADSAVE|
|Indicador|IDG_VS_TOOLSB_GAUGE|

### <a name="build-toolbar-groups"></a>Grupos de la barra de herramientas de compilación

|Nombre|ID|
|----------|--------|
|Barra de compilación|IDG_VS_BUILDBAR|
|Cancelar|IDG_VS_BUILD_CANCEL|

### <a name="text-editor-toolbar-groups"></a>Grupos de barras de herramientas del editor de texto

|Nombre|ID|
|----------|--------|
|Completion|IDM_VS_TOOL_TEXTEDITOR|
|Aplicar sangría|IDG_VS_EDITTOOLBAR_INDENT|
|Comentario|IDG_VS_EDITTOOLBAR_COMMENT|
|Marcadores|IDG_VS_EDITTOOLBAR_TEMPBOOKMARKS|

### <a name="debug-toolbar-groups"></a>Depurar grupos de barras de herramientas

|Nombre|ID|
|----------|--------|
|Ejecución|IDM_DEBUG_TOOLBAR|
|Recorrido paso a paso|IDG_DEBUG_TOOLBAR_STEPPING|
|Watch|IDG_DEBUG_TOOLBAR_WATCH|
|Windows|IDG_DEBUG_TOOLBAR_WINDOWS|

### <a name="debug-location-toolbar-groups"></a>Depurar grupos de barras de herramientas de ubicación

|Nombre|ID|
|----------|--------|
|Ubicación de depuración|IDG_DEBUG_CONTEXT_TOOLBAR|

## <a name="tool-window-toolbars"></a>Ventana de herramientas (barras de herramientas)
 Las barras de herramientas pueden aparecer directamente en el IDE o en ventanas de herramientas, como **Explorador de soluciones**. Dado que las ventanas de herramientas no están definidas en los archivos *. Vsct* , las barras de herramientas de la ventana de herramientas no tienen elementos primarios definidos. En su lugar, se colocan en el código. En la tabla siguiente se muestran las barras de herramientas que aparecen en las ventanas de herramientas del IDE de y los grupos de comandos que contienen.

> [!NOTE]
> Las barras de herramientas y los grupos usan el GUID `guidSHLMainMenu` , excepto cuando se especifica lo contrario mediante la sintaxis GUID: ID. Cuando se especifica un GUID para una barra de herramientas, también se aplica a los grupos que descienden de esa barra de herramientas.

|Ventana de herramientas|Barra de herramientas|Grupos|
|-----------------|-------------|------------|
|Explorador de soluciones|IDM_VS_TOOL_PROJWIN|IDG_VS_PROJ_TOOLBAR1.. 5|
|Explorador de servidores|guid_SE_MenuGroup: IDM_SE_TOOLBAR_SERVEREXPLORER|IDG_SE_TOOLBAR_REFRESH|
|Propiedades|IDM_VS_TOOL_PROPERTIES|IDG_VS_PROPERTIES_SORT<br /><br /> IDG_VS_PROPERTIES_PAGES|
|Vista de clases|IDM_VS_TOOL_CLASSVIEW|IDG_VS_CLASSVIEW_FOLDERS<br /><br /> IDG_VS_CLASSVIEW_SEARCH<br /><br /> IDG_VS_CLASSVIEW_SETTINGS|
|Vista de clases|IDM_VS_TOOL_CLASSVIEW_GO|IDG_VS_CLASSVIEW_SEARCH2|
|Examinador de objetos|IDM_VS_TOOL_OBJBROWSER|IDG_VS_OBJBROWSER_SUBSETS<br /><br /> IDG_VS_OBJBROWSER_SEARCH<br /><br /> IDG_VS_OBJBROWSER_ADDREFERENCE<br /><br /> IDG_VS_OBJBROWSER_BROWSERSETTINGS|
|Examinador de objetos|IDM_VS_TOOL_OBJECT_BROWSER_GO|IDG_VS_OBJBROWSER_SEARCH2|
|Output|IDM_VS_TOOL_OUTPUTWINDOW|IDG_VS_OUTPUTWINDOW_SELECT<br /><br /> IDG_VS_OUTPUTWINDOW_GOTO<br /><br /> IDG_VS_OUTPUTWINDOW_NEXTPREV<br /><br /> IDG_VS_OUTPUTWINDOW_CLEAR<br /><br /> IDG_VS_OUTPUTWINDOW_WORDWRAP|
|Buscar y reemplazar|IDM_VS_TOOL_UNIFIEDFIND|IDG_VS_FINDTAB<br /><br /> IDG_VS_REPLACETAB|
|Resultados de la búsqueda 1|IDM_VS_TOOL_FINDRESULTS1|IDG_VS_FINDRESULTS1_GOTO<br /><br /> IDG_VS_FINDRESULTS1_NEXTPREV<br /><br /> IDG_VS_FINDRESULTS1_CLEAR<br /><br /> IDG_VS_FINDRESULTS1_STOPFIND|
|Resultados de búsqueda 2|IDM_VS_TOOL_FINDRESULTS2|IDG_VS_FINDRESULTS2_GOTO<br /><br /> IDG_VS_FINDRESULTS2_NEXTPREV<br /><br /> IDG_VS_FINDRESULTS2_CLEAR<br /><br /> IDG_VS_FINDRESULTS2_STOPFIND|
|Fragmento de código|IDM_VS_TOOL_SNIPPETMENUS|IDG_VS_SNIPPET_REPL<br /><br /> IDG_VS_SNIPPET_REF<br /><br /> IDG_VS_SNIPPET_PROP|
|Marcadores|IDM_VS_TOOL_BOOKMARKWIND|IDG_VS_BWNEWFOLDER<br /><br /> IDG_VS_BWNEXTBM<br /><br /> IDG_VS_BWNEXTBMF<br /><br /> IDG_VS_BWENABLE<br /><br /> IDG_VS_BWDELETE|
|Lista de tareas|IDM_VS_TOOL_TASKLIST|IDG_VS_TASKLIST_PROVIDERLIST|
|Tareas de usuario|IDM_VS_TOOL_USERTASKS|IDG_VS_TASKLIST_PROVIDERLIST<br /><br /> IDG_VS_USERTASKS_EDIT|
|Lista de errores|IDM_VS_TOOL_ERRORLIST|IDG_VS_ERRORLIST_ERRORGROUP<br /><br /> IDG_VS_ERRORLIST_WARNINGGROUP<br /><br /> IDG_VS_ERRORLIST_MESSAGEGROUP|
|Explorador de llamadas|IDM_VS_TOOL_CALLBROWSER1.. dieciséi|IDG_VS_TOOLBAR_CALLBROWSER1_ACTIONS<br /><br /> IDG_VS_TOOLBAR_CALLBROWSER1_TYPE<br /><br /> IDG_VS_TOOLBAR_CALLBROWSER1_CBSETTINGS|
|Puntos de interrupción|guidVSDebugGroup: IDM_BREAKPOINTS_WINDOW_TOOLBAR|IDG_BREAKPOINTS_WINDOW_NEW<br /><br /> IDG_BREAKPOINTS_WINDOW_DELETE<br /><br /> IDG_BREAKPOINTS_WINDOW_ALL<br /><br /> IDG_BREAKPOINTS_WINDOW_VIEW<br /><br /> IDG_BREAKPOINTS_WINDOW_EDIT<br /><br /> IDG_BREAKPOINTS_WINDOW_COLUMNS|
|Desensamblado|guidVSDebugGroup: IDM_DISASM_WINDOW_TOOLBAR|IDG_DISASM_WINDOW_TOOLBAR|
|Memoria 1-4|guidVSDebugGroup: IDM_MEMORY_WINDOW_TOOLBAR1... 4|IDG_MEMORY_EXPRESSION1.. 4<br /><br /> IDG_MEMORY_COLUMNS1.. 4|
|Procesos|guidVSDebugGroup: IDM_ATTACHED_PROCS_TOOLBAR|IDG_ATTACHED_PROCS_EXECCNTRL IDG_ATTACHED_PROCS_STEPPING<br /><br /> IDG_ATTACHED_PROCS_EXECCNTRL2<br /><br /> IDG_ATTACHED_PROCS_ATTACH<br /><br /> IDG_ATTACHED_PROCS_COLUMNS|

## <a name="see-also"></a>Vea también
- [Agregar un controlador de menú a una barra de herramientas](../../extensibility/adding-a-menu-controller-to-a-toolbar.md)
- [Agregar una barra de herramientas a una ventana de herramientas](../../extensibility/adding-a-toolbar-to-a-tool-window.md)
- [GUID e identificadores de los menús de Visual Studio](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md)
