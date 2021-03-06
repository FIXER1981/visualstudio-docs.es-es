---
title: Cambiar la apariencia de un comando | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands, changing appearance
- menu commands, changing appearance
- menus, changing command appearance
ms.assetid: da2474fa-f92d-4e9e-b8bf-67c61bf249c2
caps.latest.revision: 24
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4741059410e052c571d77088b9cbe109fb651642
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68184507"
---
# <a name="changing-the-appearance-of-a-command"></a>Cambio de la apariencia de un comando
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Puede enviar comentarios al usuario mediante el cambio de la apariencia de un comando. Por ejemplo, puede que desee que un comando tenga un aspecto diferente cuando no esté disponible. Puede hacer que los comandos estén disponibles o no, ocultarlos o mostrarlos, o bien activarlos o desactivarlos en el menú.  
  
 Para cambiar la apariencia de un comando, realice una de estas acciones:  
  
- Especifique las marcas adecuadas en la definición de comando en el archivo de tabla de comandos.  
  
- Use el <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService> servicio.  
  
- Implemente la <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> interfaz y modifique los objetos de comando sin formato.  
  
  En los pasos siguientes se muestra cómo buscar y actualizar el aspecto de un comando mediante Managed Package Framework (MPF).  
  
### <a name="to-change-the-appearance-of-a-menu-command"></a>Para cambiar la apariencia de un comando de menú  
  
1. Siga las instrucciones que aparecen en el artículo sobre cómo [cambiar el texto de un comando de menú](../extensibility/changing-the-text-of-a-menu-command.md) para crear un elemento de menú denominado `New Text` .  
  
2. En el archivo ChangeMenuText.cs, agregue la siguiente instrucción using:  
  
    ```csharp  
    using System.Security.Permissions;  
    ```  
  
3. En el archivo ChangeMenuTextPackageGuids.cs, agregue la siguiente línea:  
  
    ```csharp  
    public const string guidChangeMenuTextPackageCmdSet= "00000000-0000-0000-0000-00000000";  // get the GUID from the .vsct file  
    ```  
  
4. En el archivo ChangeMenuText.cs, reemplace el código del método método ShowMessageBox por lo siguiente:  
  
    ```csharp  
    private void ShowMessageBox(object sender, EventArgs e)  
    {  
        var command = sender as OleMenuCommand;  
        if (command.Text == "New Text")  
            ChangeMyCommand(command.CommandID.ID, false);}  
    }  
    ```  
  
5. Obtenga el comando que desea actualizar del <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService> objeto y, a continuación, establezca las propiedades adecuadas en el objeto de comando. Por ejemplo, el siguiente método hace que el comando especificado de un conjunto de comandos VSPackage esté disponible o no disponible. El código siguiente hace que el elemento de menú denominado `New Text` no esté disponible después de hacer clic en él.  
  
    ```csharp  
    public bool ChangeMyCommand(int cmdID, bool enableCmd)  
    {  
        bool cmdUpdated = false;  
        var mcs = this.ServiceProvider.GetService(typeof(IMenuCommandService))  
            as OleMenuCommandService;  
        var newCmdID = new CommandID(new Guid(ChangeMenuTextPackageGuids.guidChangeMenuTextPackageCmdSet), cmdID);  
        MenuCommand mc = mcs.FindCommand(newCmdID);  
        if (mc != null)  
        {  
            mc.Enabled = enableCmd;  
            cmdUpdated = true;  
        }  
        return cmdUpdated;    }  
    }  
    ```  
  
6. Compile la solución y comience la depuración. Debería aparecer la instancia experimental de Visual Studio.  
  
7. En el menú **herramientas** , haga clic en el comando **invocar ChangeMenuText** . En este punto, el nombre de comando es **Invoke ChangeMenuText**, por lo que el controlador de comandos no llama a ChangeMyCommand ().  
  
8. En el menú **herramientas** , ahora debería ver el **nuevo texto**. Haga clic en **nuevo texto**. El comando debería aparecer ahora atenuado.  
  
## <a name="see-also"></a>Consulte también  
 [Comandos, menús y barras de herramientas](../extensibility/internals/commands-menus-and-toolbars.md)   
 [Cómo agrega VSPackages los elementos de la interfaz de usuario](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Extensión de menús y comandos](../extensibility/extending-menus-and-commands.md)   
 [Archivos de tabla de comandos de Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
