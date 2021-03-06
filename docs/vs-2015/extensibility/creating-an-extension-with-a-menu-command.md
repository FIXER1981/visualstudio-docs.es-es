---
title: Crear una extensión con un comando de menú | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- write a vspackage
- vspackage
- tutorials
- visual studio package
ms.assetid: f97104c8-2bcb-45c7-a3c9-85abeda8df98
caps.latest.revision: 57
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e3bbf6b3b1ed2565d5e58806bd0935f713ba5bfd
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "62572892"
---
# <a name="creating-an-extension-with-a-menu-command"></a>Creación de una extensión con un comando de menú
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

En este tutorial se muestra cómo crear una extensión con un comando de menú que inicia el Bloc de notas.  
  
## <a name="prerequisites"></a>Prerrequisitos  
 A partir de Visual Studio 2015, no se instala el SDK de Visual Studio desde el centro de descarga. Se incluye como una característica opcional en el programa de instalación de Visual Studio. También puede instalar el SDK de VS más adelante. Para obtener más información, vea [instalar el SDK de Visual Studio](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-menu-command"></a>Crear un comando de menú  
  
1. Cree un proyecto VSIX denominado **FirstMenuCommand**. Puede encontrar la plantilla de Proyecto VSIX en el cuadro de diálogo **nuevo proyecto** en **Visual C#/extensibilidad**.  
  
2. Cuando se abra el proyecto, agregue una plantilla de elemento de comando personalizada denominada **FirstCommand**. En el **Explorador de soluciones**, haga clic con el botón secundario en el nodo del proyecto y seleccione **Agregar o nuevo elemento**. En el cuadro de diálogo **Agregar nuevo elemento** , vaya a **Visual C#/extensibilidad** y seleccione **comando personalizado**. En el campo **nombre** situado en la parte inferior de la ventana, cambie el nombre del archivo de comandos a **FirstCommand.CS**.  
  
3. Compile la solución y comience la depuración.  
  
     Aparece la instancia experimental de Visual Studio. Para obtener más información sobre la instancia experimental, vea [la instancia experimental](../extensibility/the-experimental-instance.md).  
  
4. En la instancia experimental, abra la ventana  **herramientas/extensiones y actualizaciones** . Debería ver la extensión **FirstMenuCommand** aquí. (Si abre **extensiones y actualizaciones** en la instancia de trabajo de Visual Studio, no verá **FirstMenuCommand**).  
  
     Ahora, vaya al menú **herramientas** en la instancia experimental. Debería ver el comando **Invoke FirstCommand** . En este momento, solo muestra un cuadro de mensaje que dice "FirstCommandPackage dentro de FirstMenuCommand. FirstCommand. MenuItemCallback ()". Veremos cómo iniciar realmente el Bloc de notas desde este comando en la sección siguiente.  
  
## <a name="changing-the-menu-command-handler"></a>Cambiar el controlador de comandos de menú  
 Ahora vamos a actualizar el controlador de comandos para iniciar el Bloc de notas.  
  
1. Detenga la depuración y vuelva a la instancia de trabajo de Visual Studio. Abra el archivo FirstCommand.cs y agregue la siguiente instrucción using:  
  
    ```csharp  
    using System.Diagnostics;  
    ```  
  
2. Busque el constructor FirstCommand privado. Aquí es donde el comando se enlaza al servicio de comandos y se especifica el controlador de comandos. Cambie el nombre del controlador de comandos a StartNotepad, como se indica a continuación:  
  
    ```csharp  
    private FirstCommand(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException(nameof(package));  
        }  
  
        this.package = package;  
  
         OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
        if (commandService != null)  
        {  
            CommandID menuCommandID = new CommandID(CommandSet, CommandId);  
            // Change to StartNotepad handler.  
            MenuCommand menuItem = new MenuCommand(this.StartNotepad, menuCommandID);  
            commandService.AddCommand(menuItem);  
        }  
    }  
    ```  
  
3. Quite el método MenuItemCallback y agregue un método StartNotepad que solo iniciará el Bloc de notas:  
  
    ```csharp  
    private void StartNotepad(object sender, EventArgs e)  
    {  
        Process proc = new Process();  
        proc.StartInfo.FileName = "notepad.exe";  
        proc.Start();  
    }  
    ```  
  
4. Pruébelo ahora. Cuando empiece a depurar el proyecto y haga clic en **herramientas/invocación FirstCommand**, debería aparecer una instancia del Bloc de notas.  
  
     Puede usar una instancia de la <xref:System.Diagnostics.Process> clase para ejecutar cualquier archivo ejecutable, no solo el Bloc de notas. Pruébelo con calc.exe, por ejemplo.  
  
## <a name="cleaning-up-the-experimental-environment"></a>Limpieza del entorno experimental  
 Si está desarrollando varias extensiones o solo está explorando los resultados con versiones diferentes del código de extensión, el entorno experimental puede dejar de funcionar de la manera que debería. En este caso, debe ejecutar el script de restablecimiento. Se le llama **restablecer la instancia experimental de Visual studio 2015**y se incluye como parte del SDK de Visual Studio. Este script quita todas las referencias a las extensiones del entorno experimental, por lo que puede empezar desde cero.  
  
 Puede obtener acceso a este script de una de estas dos maneras:  
  
1. En el escritorio, busque **restablecer la instancia experimental de Visual Studio 2015**.  
  
2. Ejecute lo siguiente desde la línea de comandos:  
  
    ```  
    <VSSDK installation>\VisualStudioIntegration\Tools\Bin\CreateExpInstance.exe /Reset /VSInstance=14.0 /RootSuffix=Exp && PAUSE  
  
    ```  
  
## <a name="deploying-your-extension"></a>Implementación de la extensión  
 Ahora que la extensión de la herramienta se ejecuta de la manera que desea, es el momento de pensar en compartirla con sus amigos y compañeros. Esto es fácil, siempre y cuando tenga Visual Studio 2015 instalado. Lo único que tiene que hacer es enviarles el archivo. vsix que compiló. (Asegúrese de compilarlo en modo de versión).  
  
 Puede encontrar el archivo. VSIX para esta extensión en el directorio FirstMenuCommand bin. En concreto, suponiendo que haya compilado la configuración de lanzamiento, estará en:  
  
 **\<code directory>\FirstMenuCommand\FirstMenuCommand\bin\Release\ FirstMenuCommand. vsix**  
  
 Para instalar la extensión, el amigo debe cerrar todas las instancias abiertas de Visual Studio y, a continuación, hacer doble clic en el archivo. vsix, que abre el **instalador de VSIX**. Los archivos se copian en el directorio **%LocalAppData%\Microsoft\VisualStudio\14.0\Extensions**  
  
 Cuando el amigo vuelva a mostrar Visual Studio, encontrará la extensión FirstMenuCommand en **herramientas/extensiones y actualizaciones**. También puede ir a **extensiones y actualizaciones** para desinstalar o deshabilitar la extensión.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Este tutorial le ha mostrado solo una pequeña parte de lo que puede hacer con una extensión de Visual Studio. Esta es una breve lista de otras cosas (razonablemente fácil) que puede hacer con las extensiones de Visual Studio:  
  
1. Puede hacer muchas más cosas con un comando de menú simple:  
  
   1. Agregar su propio icono: [Agregar iconos a comandos de menú](../extensibility/adding-icons-to-menu-commands.md)  
  
   2. Cambiar el texto del comando de menú: [cambiar el texto de un comando de menú](../extensibility/changing-the-text-of-a-menu-command.md)  
  
   3. Agregar un acceso directo de menú a un comando: [enlazar métodos abreviados de teclado a elementos de menú](../extensibility/binding-keyboard-shortcuts-to-menu-items.md)  
  
2. Agregar diferentes tipos de comandos, menús y barras de herramientas: [extensión de menús y comandos](../extensibility/extending-menus-and-commands.md)  
  
3. Agregar ventanas de herramientas y extender las ventanas de herramientas integradas de Visual Studio: [extender y personalizar ventanas de herramientas](../extensibility/extending-and-customizing-tool-windows.md)  
  
4. Agregar IntelliSense, sugerencias de código y otras características a los editores de código existentes: [extensión de los servicios de lenguaje y editor](../extensibility/extending-the-editor-and-language-services.md)  
  
5. Agregar opciones y páginas de propiedades y la configuración de usuario a la extensión: [extensión de propiedades y la ventana de propiedades](../extensibility/extending-properties-and-the-property-window.md) , y extensión de la [configuración de usuario y las opciones](../extensibility/extending-user-settings-and-options.md)  
  
   Otros tipos de extensiones requieren un poco más de trabajo, como la creación de un nuevo tipo de proyecto ([extensión de proyectos](../extensibility/extending-projects.md)), la creación de un nuevo tipo de editor ([creación de editores y diseñadores personalizados](../extensibility/creating-custom-editors-and-designers.md)) o la implementación de la extensión en un shell aislado: [Shell aislado de Visual Studio](../extensibility/visual-studio-isolated-shell.md)
