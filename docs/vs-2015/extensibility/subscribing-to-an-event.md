---
title: Suscribirse a un evento | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- running document table (RDT), responding to events
- running document table (RDT), subscribing to events
ms.assetid: e94a4fea-94df-488e-8560-9538413422bc
caps.latest.revision: 36
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 324e74c78f01da47c544b5f640ad0bd9052a1bb4
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68160556"
---
# <a name="subscribing-to-an-event"></a>Suscripción a un evento
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

En este tutorial se explica cómo crear una ventana de herramientas que responda a los eventos de una tabla de documentos en ejecución (RDT). Una ventana de herramientas hospeda un control de usuario que implementa <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents> . El <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.AdviseRunningDocTableEvents%2A> método conecta la interfaz con los eventos.  
  
## <a name="prerequisites"></a>Prerrequisitos  
 A partir de Visual Studio 2015, no se instala el SDK de Visual Studio desde el centro de descarga. Se incluye como una característica opcional en el programa de instalación de Visual Studio. También puede instalar el SDK de VS más adelante. Para obtener más información, vea [instalar el SDK de Visual Studio](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="subscribing-to-rdt-events"></a>Suscripción a eventos RDT  
  
#### <a name="to-create-an-extension-with-a-tool-window"></a>Para crear una extensión con una ventana de herramientas  
  
1. Cree un proyecto denominado **RDTExplorer** mediante la plantilla VSIX y agregue una plantilla de elemento de ventana de herramientas personalizada denominada **RDTExplorerWindow**.  
  
     Para obtener más información sobre cómo crear una extensión con una ventana de herramientas, vea [crear una extensión con una ventana de herramientas](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
#### <a name="to-subscribe-to-rdt-events"></a>Para suscribirse a eventos de RDT  
  
1. Abra el archivo RDTExplorerWindowControl. XAML y elimine el botón denominado `button1` . Agregue un <xref:System.Windows.Forms.ListBox> control y acepte el nombre predeterminado. El elemento Grid debe tener el siguiente aspecto:  
  
    ```xml  
    <Grid>  
        <StackPanel Orientation="Vertical" Margin="-10,10,10,0">  
            <TextBlock Margin="10" HorizontalAlignment="Center">RDTExplorerWindow</TextBlock>  
            <ListBox x:Name="listBox" Height="100" />  
        </StackPanel>  
    </Grid>  
    ```  
  
2. Abra el archivo RDTExplorerWindow.cs en la vista de código. Agregue las siguientes instrucciones using al principio del archivo.  
  
    ```csharp  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.Shell;  
    using Microsoft.VisualStudio.Shell.Interop;  
    ```  
  
3. Modifique la `RDTExplorerWindow` clase para que, además de derivar de la <xref:Microsoft.VisualStudio.Shell.ToolWindowPane> clase, implemente la <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents> interfaz.  
  
    ```csharp  
    public class RDTExplorerWindow : ToolWindowPane, IVsRunningDocTableEvents  
    {. . .}  
    ```  
  
4. Implemente <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents>.  
  
    - Implemente la interfaz. Coloque el cursor en el nombre de IVsRunningDocTableEvents. Debería ver una bombilla en el margen izquierdo. Haga clic en la flecha hacia abajo situada a la derecha de la bombilla y seleccione **implementar interfaz**.  
  
5. En cada método de la interfaz, reemplace la línea `throw new NotImplementedException();` por lo siguiente:  
  
    ```csharp  
    return VSConstants.S_OK;  
    ```  
  
6. Agregue un campo de cookie a la clase RDTExplorerWindow.  
  
    ```csharp  
    private uint rdtCookie;   
    ```  
  
     Esto contiene la cookie devuelta por el <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.AdviseRunningDocTableEvents%2A> método.  
  
7. Invalide el método Initialize () de RDTExplorerWindow para registrar los eventos RDT. Siempre debe obtener los servicios en el método Initialize () de ToolWindowPane, no en el constructor.  
  
    ```csharp  
    protected override void Initialize()  
    {  
        IVsRunningDocumentTable rdt = (IVsRunningDocumentTable)  
        this.GetService(typeof(SVsRunningDocumentTable));  
        rdt.AdviseRunningDocTableEvents(this, out rdtCookie);  
    }  
    ```  
  
     <xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>Se llama al servicio para obtener una <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable> interfaz. El <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.AdviseRunningDocTableEvents%2A> método conecta eventos RDT a un objeto que implementa <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents> , en este caso, un objeto RDTExplorer.  
  
8. Actualice el método Dispose () de RDTExplorerWindow.  
  
    ```csharp  
    protected override void Dispose(bool disposing)  
    {  
        // Release the RDT cookie.  
        IVsRunningDocumentTable rdt = (IVsRunningDocumentTable)  
            Package.GetGlobalService(typeof(SVsRunningDocumentTable));  
        rdt.UnadviseRunningDocTableEvents(rdtCookie);  
  
        base.Dispose(disposing);  
    }  
    ```  
  
     El <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.UnadviseRunningDocTableEvents%2A> método elimina la conexión entre `RDTExplorer` y la notificación de eventos RDT.  
  
9. Agregue la siguiente línea al cuerpo del <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents.OnBeforeLastDocumentUnlock%2A> controlador, justo antes de la `return` instrucción.  
  
    ```csharp  
    public int OnBeforeLastDocumentUnlock(uint docCookie, uint dwRDTLockType, uint dwReadLocksRemaining, uint dwEditLocksRemaining)  
    {  
        ((RDTExplorerWindowControl)this.Content).listBox.Items.Add("Entering OnBeforeLastDocumentUnlock");  
        return VSConstants.S_OK;  
    }  
    ```  
  
10. Agregue una línea similar al cuerpo del <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents.OnAfterFirstDocumentLock%2A> controlador y a otros eventos que desee ver en el cuadro de lista.  
  
    ```csharp  
    public int OnAfterFirstDocumentLock(uint docCookie, uint dwRDTLockType, uint dwReadLocksRemaining, uint dwEditLocksRemaining)  
    {  
        ((RDTExplorerWindowControl)this.Content).listBox.Items.Add("Entering OnAfterFirstDocumentLock");  
        return VSConstants.S_OK;  
    }  
    ```  
  
11. Compile la solución y comience la depuración. Aparece la instancia experimental de Visual Studio.  
  
12. Abra **RDTExplorerWindow** (**Ver/otras ventanas/RDTExplorerWindow**).  
  
     La ventana **RDTExplorerWindow** se abre con una lista de eventos vacía.  
  
13. Abra o cree una solución.  
  
     A medida que `OnBeforeLastDocument` `OnAfterFirstDocument` se activan los eventos y, la notificación de cada evento aparece en la lista de eventos.
