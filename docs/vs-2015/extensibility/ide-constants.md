---
title: Constantes de IDE | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDE, errors
- logical views
- errors [Visual Studio], IDE
- UI context constants
- constants, Visual Studio IDE
- IDE, constants
- physical views
ms.assetid: 5030e70a-241d-474a-ba8c-e3b1cf947ff0
caps.latest.revision: 24
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 18256996d829d34117caa11f4e581d8e54d738b1
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68204037"
---
# <a name="ide-constants"></a>Constantes de IDE
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La <xref:Microsoft.VisualStudio.VSConstants> clase proporciona constantes que son específicas del entorno de desarrollo integrado (IDE) y que se definieron previamente solo en los archivos de encabezado.  
  
## <a name="logical-and-physical-views"></a>Vistas lógicas y físicas  
  
|Value|Descripción|  
|-----------|-----------------|  
|[LOGVIEWID_Code_guid](/dotnet/api/microsoft.visualstudio.vsconstants.logviewid.code_guid?view=visualstudiosdk-2015)|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>los `cmdidOpenWith` controladores deben pasar este valor al <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> método para obtener el cuadro de diálogo **abrir con** , en este caso en posibles vistas de código.|  
|[LOGVIEWID_Debugging_guid](/dotnet/api/microsoft.visualstudio.vsconstants.logviewid.debugging_guid?view=visualstudiosdk-2015)|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>los `cmdidOpenWith` Controladores pasan este valor al <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> método para obtener el cuadro de diálogo **abrir con** , en este caso rellenado con posibles <xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Debugging_guid> vistas de depuración que se asignan a la misma vista que <xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Code_guid> .|  
|[LOGVIEWID_Designer_guid](/dotnet/api/microsoft.visualstudio.vsconstants.logviewid.designer_guid?view=visualstudiosdk-2015)|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>`cmdidOpenWith`los controladores pasan este valor al <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> método para obtener el cuadro de diálogo **abrir con** , en este caso para **Ver** las vistas del diseñador de formularios.|  
|[LOGVIEWID_Primary_guid](/dotnet/api/microsoft.visualstudio.vsconstants.logviewid.primary_guid?view=visualstudiosdk-2015)|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>los `cmdidOpenWith` Controladores pasan este valor al <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> método para obtener el cuadro de diálogo **abrir con** , en este caso la vista predeterminada/primaria del generador de editores.|  
|[LOGVIEWID_TextView_guid](/dotnet/api/microsoft.visualstudio.vsconstants.logviewid.textview_guid?view=visualstudiosdk-2015)|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>los `cmdidOpenWith` Controladores pasan este valor al <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> método para obtener el cuadro de diálogo **abrir con** , en este caso de un documento o una vista del editor de texto de datos.|  
|[LOGVIEWID_UserChooseView_guid](/dotnet/api/microsoft.visualstudio.vsconstants.logviewid.userchooseview_guid?view=visualstudiosdk-2015)|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>los `cmdidOpenWith` Controladores pasan este valor al <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> método, que solicita al usuario que elija la vista definida por el usuario que se va a usar.|  
  
## <a name="editor-factory-flags"></a>Marcas de generador de editores  
  
|Value|Descripción|  
|-----------|-----------------|  
|[CEF. CloneFile](/dotnet/api/microsoft.visualstudio.vsconstants.cef?view=visualstudiosdk-2015)|Marca obsoleta combinada como el primer parámetro del <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> método.|  
|[CEF. CloneFile](/dotnet/api/microsoft.visualstudio.vsconstants.cef?view=visualstudiosdk-2015)|Bit a bit combinado como primer parámetro del <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> método, esto indica que el generador de editores debe realizar las correcciones necesarias.|  
|[CEF. CloneFile](/dotnet/api/microsoft.visualstudio.vsconstants.cef?view=visualstudiosdk-2015)|Bit a bit combinado como primer parámetro del <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> método, esta marca es mutuamente excluyente de [CEF. CloneFile](/dotnet/api/microsoft.visualstudio.vsconstants.cef?view=visualstudiosdk-2015).|  
|[CEF. CloneFile](/dotnet/api/microsoft.visualstudio.vsconstants.cef?view=visualstudiosdk-2015)|Bit a bit combinado como primer parámetro del <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> método, esto indica que el generador de editores debe crear el editor sin mostrar una interfaz de usuario (UI).|  
  
## <a name="visual-studio-errors"></a>Errores de Visual Studio  
  
|Value|Descripción|  
|-----------|-----------------|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_BUSY>|Constante devuelta por las interfaces a un comportamiento asincrónico cuando el objeto en cuestión está en estado ocupado.|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA>|Un valor HRESULT de error específico de Visual Studio para "datos de documento incompatibles".|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PACKAGENOTLOADED>|Un valor HRESULT de error específico de Visual Studio que indica "paquete no cargado".|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTALREADYEXISTS>|Un valor HRESULT de error específico de Visual Studio que indica que el proyecto ya existe.|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTMIGRATIONFAILED>|Un valor HRESULT de error específico de Visual Studio que indica "error en la configuración del proyecto".|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTNOTLOADED>|Un valor HRESULT de error específico de Visual Studio que indica "proyecto no cargado".|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SOLUTIONALREADYOPEN>|Un valor HRESULT de error específico de Visual Studio que indica "la solución ya está abierta".|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SOLUTIONNOTOPEN>|Un valor HRESULT de error específico de Visual Studio que indica "solución no abierta".|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SPECIFYING_OUTPUT_UNSUPPORTED>|Se devuelven mediante interfaces de compilación que tienen parámetros para especificar una matriz de la <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutput> interfaz, pero la implementación solo puede aplicar el método a todas las salidas.|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_UNSUPPORTEDFORMAT>|El <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> método devuelve este valor si el documento tiene un formato que no se puede abrir en el editor.|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_WIZARDBACKBUTTONPRESS>|Un valor HRESULT que indica que el usuario ha presionado el botón atrás en un asistente de Visual Studio.|  
  
## <a name="visual-studio-constants"></a>Constantes de Visual Studio  
  
|Value|Descripción|  
|-----------|-----------------|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_S_PROJECTFORWARDED>|Un valor HRESULT de error específico de Visual Studio que indica "proyecto reenviado".|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_S_TBXMARKER>|Una constante específica de Visual Studio para un "marcador del cuadro de herramientas".|  
|<xref:Microsoft.VisualStudio.VSConstants.VSM_ENTERMODAL>|Constante que es específica de Visual Studio para difundir un mensaje de notificación a través del <xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A> método, que indica el principio de la modalidad.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSM_EXITMODAL>|Constante que es específica de Visual Studio para difundir un mensaje de notificación a través del <xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A> método que indica el final de la modalidad.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSM_TOOLBARMETRICSCHANGE>|Constante que es específica de Visual Studio para difundir un mensaje de notificación a través del <xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A> método que indica que las métricas de la barra de comandos han cambiado.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSCOOKIE_NIL>|Una constante específica de Visual Studio que indica que no se ha establecido una cookie.|  
|[VSITEMID. Nulo](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Nil>)|Identificador de elemento de Visual Studio que representa la ausencia de un elemento de proyecto. Este valor se usa cuando no hay ninguna selección actual.|
|[VSITEMID. Raíces](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)|Un identificador de elemento de Visual Studio que representa la raíz de una jerarquía de proyecto y se usa para identificar toda la jerarquía, en lugar de un único elemento.|
|[VSITEMID. Seleccione](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Selection>)|Identificador de elemento de Visual Studio que representa el elemento o elementos seleccionados actualmente, que pueden incluir la raíz de la jerarquía.| 
  
## <a name="ivsselectionevents"></a>IVsSelectionEvents  
 Describe el componente del IDE que se acaba de seleccionar, por ejemplo, en una <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A> llamada.  
  
|Constante|Value|
|--------------|-----------|
|[SelectionElement.DocumentFrame](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_DocumentFrame>)|0x2|
|[SelectionElement.PropertyBrowserSID](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_PropertyBrowserSID>)|0x4|
|[SelectionElement. proyecto](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_StartupProject>)|0x3|
|[SelectionElement. UndoManager](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_UndoManager>)|0x0|
|[SelectionElement. UserContext](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_UserContext>)|0X5|
|[SelectionElement. WindowFrame](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_WindowFrame>)|0x1| 
  
## <a name="vsselelemid"></a>VSSELELEMID  
 Constantes que se usan para indicar un nuevo estado de selección.  
  
|Constante|Value|  
|--------------|-----------|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|2|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|7|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|4|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|6|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|3|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|0|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|5|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|1|  
  
## <a name="component-selector-dialog-constants"></a>Constantes de cuadro de diálogo de selector de componentes  
  
|Constante|Value|  
|--------------|-----------|  
|<xref:Microsoft.VisualStudio.VSConstants.CPDN_SELCHANGED>|WM_USER + 1280|  
|<xref:Microsoft.VisualStudio.VSConstants.CPDN_SELDBLCLICK>|WM_USER + 1281|  
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_CLEARSELECTION>|WM_USER + 1290|  
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_GETSELECTION>|WM_USER + 1287|  
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_INITIALIZELIST>|WM_USER + 1285|  
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_INITIALIZETAB>|WM_USER + 1288|  
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_QUERYCANSELECT>|WM_USER + 1286|  
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_SETMULTISELECT>|WM_USER + 1289|  
  
## <a name="see-also"></a>Consulte también  
 [Comandos definidos por el IDE para ampliar sistemas del proyecto](../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)
