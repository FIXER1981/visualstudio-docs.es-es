---
title: Abrir una ventana de herramientas dinámica | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- tool windows, dynamic
ms.assetid: 21547ba7-6e81-44df-9277-265bf34f877a
caps.latest.revision: 22
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 09b81294abc708cf7616dad03b5dd7333d6a1719
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "90842967"
---
# <a name="opening-a-dynamic-tool-window"></a>Apertura de una ventana de herramientas dinámica
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Las ventanas de herramientas normalmente se abren desde un comando de un menú o un método abreviado de teclado equivalente. Sin embargo, en ocasiones, es posible que necesite una ventana de herramientas que se abra cada vez que se aplique un contexto de interfaz de usuario específico y se cierre cuando el contexto de la interfaz de usuario ya no se aplique. Las ventanas de herramientas como estas se denominan *dinámicas* o *automáticas*.  
  
> [!NOTE]
> Para obtener una lista de contextos de la interfaz de usuario predefinidos, vea <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT> . Como  
  
 Si desea abrir una ventana de herramientas dinámica en el inicio y es posible que se produzca un error en la creación, debe implementar la <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackageDynamicToolOwnerEx> interfaz y probar las condiciones de error en el <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackageDynamicToolOwnerEx.QueryShowTool%2A> método. Para que el shell sepa que tiene una ventana de herramientas dinámica que debe abrirse en el inicio, debe agregar el `SupportsDynamicToolOwner` valor (establecido en 1) al registro del paquete. Este valor no forma parte del estándar <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> , por lo que debe crear un atributo personalizado para agregarlo. Para obtener más información sobre los atributos personalizados, vea [usar un atributo de registro personalizado para registrar una extensión](../misc/using-a-custom-registration-attribute-to-register-an-extension.md).  
  
 Use <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> para abrir una ventana de herramientas. La ventana de herramientas se crea según sea necesario.  
  
> [!NOTE]
> El usuario puede cerrar una ventana de herramientas dinámica. Si desea crear un comando de menú para que el usuario pueda volver a abrir la ventana de herramientas, el comando de menú debe estar habilitado en el mismo contexto de la interfaz de usuario que abre la ventana de herramientas y deshabilitarse en caso contrario.  
  
### <a name="to-open-a-dynamic-tool-window"></a>Para abrir una ventana de herramientas dinámica  
  
1. Cree un proyecto VSIX denominado **DynamicToolWindow** y agregue una plantilla de elemento de ventana de herramientas denominada **DynamicWindowPane.CS**. Para obtener más información, vea [crear una extensión con una ventana de herramientas](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
2. En el archivo DynamicWindowPanePackage.cs, busque la declaración DynamicWindowPanePackage. Agregue los <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> atributos y T:Microsoft.VisualStudio.Shell.ProvideToolWindowVisibilityAttribute para registrar la ventana de herramientas.  
  
    ```vb  
    [[ProvideToolWindow(typeof(DynamicWindowPane)]  
    [ProvideToolWindowVisibility(typeof(DynamicWindowPane), VSConstants.UICONTEXT.SolutionExists_string)]  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About  
    [ProvideMenuResource("Menus.ctmenu", 1)]  
    [ProvideToolWindow(typeof(DynamicToolWindow.DynamicWindowPane))]  
    [Guid(DynamicWindowPanePackageGuids.PackageGuidString)]  
    public sealed class DynamicWindowPanePackage : Package  
    {. . .}  
    ```  
  
     Esto registra la ventana de herramientas denominada DynamicWindowPane como una ventana transitoria que no se conserva cuando Visual Studio se cierra y se vuelve a abrir. DynamicWindowPane se abre siempre que <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionExists_string> se aplica y se cierra en caso contrario.  
  
3. Compile la solución y comience la depuración. Debería aparecer la instancia experimental. No debería ver la ventana de herramientas.  
  
4. Abra un proyecto en la instancia experimental. Debería aparecer la ventana de herramientas.
