---
title: Crear una ventana de herramientas de varias instancias | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- multi
- tool windows
ms.assetid: 4a7872f1-acc9-4f43-8932-5a526b36adea
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0dcdfe3f6e488514bb2ee1ca950e952b16039b42
ms.sourcegitcommit: 4ae5e9817ad13edd05425febb322b5be6d3c3425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2020
ms.locfileid: "91102529"
---
# <a name="creating-a-multi-instance-tool-window"></a>Creación de una ventana de herramientas de varias instancias
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Puede programar una ventana de herramientas para que se puedan abrir varias instancias de ella simultáneamente. De forma predeterminada, las ventanas de herramientas solo pueden tener una instancia abierta.  
  
 Cuando se usa una ventana de herramientas de varias instancias, se pueden mostrar al mismo tiempo varios orígenes de información relacionados. Por ejemplo, podría colocar un control de varias líneas <xref:System.Windows.Forms.TextBox> en una ventana de herramientas de varias instancias para que varios fragmentos de código estén disponibles simultáneamente durante una sesión de programación. Además, por ejemplo, puede colocar un <xref:System.Windows.Forms.DataGrid> control y un cuadro de lista desplegable en una ventana de herramientas de varias instancias para que se pueda realizar un seguimiento de varios orígenes de datos en tiempo real simultáneamente.  
  
## <a name="creating-a-basic-single-instance-tool-window"></a>Crear una ventana de herramientas básica (instancia única)  
  
1. Cree un proyecto denominado **MultiInstanceToolWindow** mediante la plantilla VSIX y agregue una plantilla de elemento de ventana de herramientas personalizada denominada **MIToolWindow**.  
  
    > [!NOTE]
    > Para obtener más información sobre cómo crear una extensión con una ventana de herramientas, vea [crear una extensión con una ventana de herramientas](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
## <a name="making-a-tool-window-multi-instance"></a>Crear una ventana de herramientas de varias instancias  
  
1. Abra el archivo **MIToolWindowPackage.CS** y busque el `ProvideToolWindow` atributo. y el `MultiInstances=true` parámetro, tal y como se muestra en el ejemplo siguiente.  
  
    ```csharp  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
        [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About  
        [ProvideMenuResource("Menus.ctmenu", 1)]  
        [ProvideToolWindow(typeof(MultiInstanceToolWindow.MIToolWindow), MultiInstances = true)]  
        [Guid(MIToolWindowPackageGuids.PackageGuidString)]  
        public sealed class MIToolWindowPackage : Package  
    {. . .}  
    ```  
  
2. En el archivo MIToolWindowCommand.cs, busque el método ShowToolWindos (). En este método, llame al <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> método y establezca su `create` marca en para `false` que recorra en iteración las instancias existentes de la ventana de herramientas hasta que encuentre un disponible `id` .  
  
3. Para crear una instancia de la ventana de herramientas, llame al <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> método y establezca su `id` en un valor disponible y su `create` marca en `true` .  
  
     De forma predeterminada, el valor del `id` parámetro del <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> método es `0` . Esto crea una ventana de herramientas de una sola instancia. Para hospedar más de una instancia, cada instancia debe tener su propio único `id` .  
  
4. Llame al <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> método en el <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> objeto devuelto por la <xref:Microsoft.VisualStudio.Shell.ToolWindowPane.Frame%2A> propiedad de la instancia de la ventana de herramientas.  
  
5. De forma predeterminada, el `ShowToolWindow` método creado por la plantilla de elementos de la ventana de herramientas crea una ventana de herramientas de una sola instancia. En el ejemplo siguiente se muestra cómo modificar el `ShowToolWindow` método para crear varias instancias.  
  
    ```csharp  
    private void ShowToolWindow(object sender, EventArgs e)  
    {  
        for (int i = 0; i < 10; i++)  
        {  
            ToolWindowPane window = this.package.FindToolWindow(typeof(MIToolWindow), i, false);  
            if (window == null)  
            {  
                // Create the window with the first free ID.   
                window = (ToolWindowPane)this.package.FindToolWindow(typeof(MIToolWindow), i, true);  
                if ((null == window) || (null == window.Frame))  
                {  
                    throw new NotSupportedException("Cannot create tool window");  
                }  
  
            IVsWindowFrame windowFrame = (IVsWindowFrame)window.Frame;  
            Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(windowFrame.Show());  
            break;  
            }  
        }  
    }  
    ```
