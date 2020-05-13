---
title: Adición dinámica de elementos de menú ( Menu Items) Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- DYNAMICITEMSTART
- menu items, adding dynamically
- menus, adding dynamic items
ms.assetid: d281e9c9-b289-4d64-8d0a-094bac6c333c
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4387c1930e09e49c0ec5c36ccedc1bb83dc273f3
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2020
ms.locfileid: "80712064"
---
# <a name="dynamically-add-menu-items"></a>Añadir elementos de menú de forma dinámica
Puede agregar elementos de menú en `DynamicItemStart` tiempo de ejecución especificando el indicador de comando en una definición de botón de marcador de posición en el archivo de tabla de comandos de Visual Studio (*.vsct*) y, a continuación, definiendo (en código) el número de elementos de menú para mostrar y controlar los comandos. Cuando se carga el VSPackage, el marcador de posición se reemplaza por los elementos de menú dinámico.

 Visual Studio usa listas dinámicas en la lista **Usado más recientemente** (MRU), que muestra los nombres de los documentos que se han abierto recientemente, y la lista de **Windows,** que muestra los nombres de las ventanas que están abiertas actualmente.   El `DynamicItemStart` indicador en una definición de comando especifica que el comando es un marcador de posición hasta que se abre el VSPackage. Cuando se abre el VSPackage, el marcador de posición se reemplaza por 0 o más comandos que se crean en tiempo de ejecución y se agregan a la lista dinámica. Es posible que no pueda ver la posición en el menú donde aparece la lista dinámica hasta que se abre el VSPackage.  Para rellenar la lista dinámica, Visual Studio pide al VSPackage que busque un comando con un identificador cuyos primeros caracteres son los mismos que el identificador del marcador de posición. Cuando Visual Studio encuentra un comando coincidente, agrega el nombre del comando a la lista dinámica. A continuación, incrementa el ID y busca otro comando coincidente para agregar a la lista dinámica hasta que no haya más comandos dinámicos.

 En este tutorial se muestra cómo establecer el proyecto de inicio en una solución de Visual Studio con un comando en la barra de herramientas **del Explorador** de soluciones. Utiliza un controlador de menú que tiene una lista desplegable dinámica de los proyectos en la solución activa. Para evitar que este comando aparezca cuando no hay ninguna solución abierta o cuando la solución abierta solo tiene un proyecto, el VSPackage se carga solo cuando una solución tiene varios proyectos.

 Para obtener más información acerca de los archivos *.vsct,* vea Archivos de tabla de [comandos de Visual Studio (.vsct).](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

## <a name="create-an-extension-with-a-menu-command"></a>Crear una extensión con un comando de menú

1. Cree un proyecto `DynamicMenuItems`VSIX denominado .

2. Cuando se abra el proyecto, agregue una plantilla de elemento de comando personalizada y **asíse, asísaber, esClaDynamicMenu**. Para obtener más información, consulte [Crear una extensión con un comando de menú](../extensibility/creating-an-extension-with-a-menu-command.md).

## <a name="setting-up-the-elements-in-the-vsct-file"></a>Configuración de los elementos en el archivo *.vsct*
 Para crear un controlador de menú con elementos de menú dinámicos en una barra de herramientas, especifique los siguientes elementos:

- Dos grupos de comandos, uno que contiene el controlador de menú y otro que contiene los elementos de menú en la lista desplegable

- Un elemento de menú de tipo`MenuController`

- Dos botones, uno que actúa como marcador de posición para los elementos de menú y otro que proporciona el icono y la información sobre herramientas en la barra de herramientas.

1. En *DynamicMenuPackage.vsct*, defina los elementos de comando. Vaya a la sección Símbolos y reemplace los elementos IDSymbol en el bloque **guidDynamicMenuPackageCmdSet** GuidSymbol. Debe definir elementos IDSymbol para los dos grupos, el controlador de menú, el comando de marcador de posición y el comando de anclaje.

    ```xml
    <GuidSymbol name="guidDynamicMenuPackageCmdSet" value="{ your GUID here }">
        <IDSymbol name="MyToolbarItemGroup" value="0x1020" />
        <IDSymbol name="MyMenuControllerGroup" value="0x1025" />
        <IDSymbol name="MyMenuController" value ="0x1030"/>
        <IDSymbol name="cmdidMyAnchorCommand" value="0x0103" />
        <!-- NOTE: The following command expands at run time to some number of ids.
         Try not to place command ids after it (e.g. 0x0105, 0x0106).
         If you must add a command id after it, make the gap very large (e.g. 0x200) -->
        <IDSymbol name="cmdidMyDynamicStartCommand" value="0x0104" />
    </GuidSymbol>
    ```

2. En la sección Grupos, elimine los grupos existentes y agregue los dos grupos que acaba de definir:

    ```xml
    <Groups>
        <!-- The group that adds the MenuController on the Solution Explorer toolbar.
             The 0x4000 priority adds this group after the group that contains the
             Preview Selected Items button, which is normally at the far right of the toolbar. -->
        <Group guid="guidDynamicMenuPackageCmdSet" id="MyToolbarItemGroup" priority="0x4000" >
            <Parent guid="guidSHLMainMenu" id="IDM_VS_TOOL_PROJWIN" />
        </Group>
        <!-- The group for the items on the MenuController drop-down. It is added to the MenuController submenu. -->
        <Group guid="guidDynamicMenuPackageCmdSet" id="MyMenuControllerGroup" priority="0x4000" >
            <Parent guid="guidDynamicMenuPackageCmdSet" id="MyMenuController" />
        </Group>
    </Groups>
    ```

     Agregue el MenuController. Establezca el indicador de comando DynamicVisibility, ya que no siempre está visible. El ButtonText no se muestra.

    ```xml
    <Menus>
        <!-- The MenuController to display on the Solution Explorer toolbar.
             Place it in the ToolbarItemGroup.-->
        <Menu guid="guidDynamicMenuPackageCmdSet" id="MyMenuController" priority="0x1000" type="MenuController">
            <Parent guid="guidDynamicMenuPackageCmdSet" id="MyToolbarItemGroup" />
            <CommandFlag>DynamicVisibility</CommandFlag>
            <Strings>
               <ButtonText></ButtonText>
           </Strings>
        </Menu>
    </Menus>
    ```

3. Agregue dos botones, uno como marcador de posición para los elementos de menú dinámico y otro como delimitador para el MenuController.

     El elemento primario del botón de marcador de posición es **MyMenuControllerGroup**. Agregue los indicadores de comando DynamicItemStart, DynamicVisibility y TextChanges al botón de marcador de posición. El ButtonText no se muestra.

     El botón de anclaje mantiene el icono y el texto de información sobre herramientas. El elemento primario del botón de anclaje también es **MyMenuControllerGroup**. Agregue el indicador de comando NoShowOnMenuController para asegurarse de que el botón no aparece realmente en la lista desplegable del controlador de menú y el indicador de comando FixMenuController para convertirlo en el delimitador permanente.

    ```xml
    <!-- The placeholder for the dynamic items that expand to N items at run time. -->
    <Buttons>
        <Button guid="guidDynamicMenuPackageCmdSet" id="cmdidMyDynamicStartCommand" priority="0x1000" >
          <Parent guid="guidDynamicMenuPackageCmdSet" id="MyMenuControllerGroup" />
          <CommandFlag>DynamicItemStart</CommandFlag>
          <CommandFlag>DynamicVisibility</CommandFlag>
          <CommandFlag>TextChanges</CommandFlag>
          <!-- This text does not appear. -->
          <Strings>
            <ButtonText>Project</ButtonText>
          </Strings>
        </Button>

        <!-- The anchor item to supply the icon/tooltip for the MenuController -->
        <Button guid="guidDynamicMenuPackageCmdSet" id="cmdidMyAnchorCommand" priority="0x0000" >
          <Parent guid="guidDynamicMenuPackageCmdSet" id="MyMenuControllerGroup" />
          <!-- This is the icon that appears on the Solution Explorer toolbar. -->
          <Icon guid="guidImages" id="bmpPicArrows"/>
          <!-- Do not show on the menu controller's drop down list-->
          <CommandFlag>NoShowOnMenuController</CommandFlag>
          <!-- Become the permanent anchor item for the menu controller -->
          <CommandFlag>FixMenuController</CommandFlag>
          <!-- The text that appears in the tooltip.-->
          <Strings>
            <ButtonText>Set Startup Project</ButtonText>
          </Strings>
        </Button>
    </Buttons>
    ```

4. Agregue un icono al proyecto (en la carpeta *Resources)* y, a continuación, agregue la referencia a él en el archivo *.vsct.* En este tutorial, usamos el icono Flechas que se incluye en la plantilla de proyecto.

5. Agregue una sección VisibilityConstraints fuera de la sección Comandos justo antes de la sección Símbolos. (Puede recibir una advertencia si la agrega después de Símbolos.) En esta sección se asegura de que el controlador de menú solo aparece cuando se carga una solución con varios proyectos.

    ```xml
    <VisibilityConstraints>
         <!--Make the MenuController show up only when there is a solution with more than one project loaded-->
        <VisibilityItem guid="guidDynamicMenuPackageCmdSet" id="MyMenuController" context="UICONTEXT_SolutionHasMultipleProjects"/>
    </VisibilityConstraints>
    ```

## <a name="implement-the-dynamic-menu-command"></a>Implementar el comando de menú dinámico
 Cree una clase de comando de <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>menú dinámico que herede de . En esta implementación, el constructor especifica un predicado que se usará para los comandos coincidentes. Debe invalidar <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.DynamicItemMatch%2A> el método para utilizar <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.MatchedCommandId%2A> este predicado para establecer la propiedad, que identifica el comando que se va a invocar.

1. Cree un nuevo archivo de clase de C- denominado *DynamicItemMenuCommand.cs*y <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>agregue una clase denominada **DynamicItemMenuCommand** que herede de:

    ```csharp
    class DynamicItemMenuCommand : OleMenuCommand
    {

    }

    ```

2. Agregue lo siguiente mediante directivas:

    ```csharp
    using Microsoft.VisualStudio.Shell;
    using Microsoft.VisualStudio.Shell.Interop;
    using System.ComponentModel.Design;
    ```

3. Agregue un campo privado para almacenar el predicado de coincidencia:

    ```csharp
    private Predicate<int> matches;

    ```

4. Agregue un constructor que <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> herede del constructor y <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> especifique un controlador de comandos y un controlador. Agregue un predicado para hacer coincidir el comando:

    ```csharp
    public DynamicItemMenuCommand(CommandID rootId, Predicate<int> matches, EventHandler invokeHandler, EventHandler beforeQueryStatusHandler)
        : base(invokeHandler, null /*changeHandler*/, beforeQueryStatusHandler, rootId)
    {
        if (matches == null)
        {
            throw new ArgumentNullException("matches");
        }

        this.matches = matches;
    }
    ```

5. Invalide <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.DynamicItemMatch%2A> el método para que llame <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.MatchedCommandId%2A> al predicado de coincidencias y establezca la propiedad:

    ```csharp
    public override bool DynamicItemMatch(int cmdId)
    {
        // Call the supplied predicate to test whether the given cmdId is a match.
        // If it is, store the command id in MatchedCommandid
        // for use by any BeforeQueryStatus handlers, and then return that it is a match.
        // Otherwise clear any previously stored matched cmdId and return that it is not a match.
        if (this.matches(cmdId))
        {
            this.MatchedCommandId = cmdId;
            return true;
        }

        this.MatchedCommandId = 0;
        return false;
    }
    ```

## <a name="add-the-command"></a>Añadir el comando
 El DynamicMenu constructor es donde se configuran los comandos de menú, incluidos los menús dinámicos y los elementos de menú.

1. En *DynamicMenuPackage.cs*, agregue el GUID del conjunto de comandos y el identificador de comando:

    ```csharp
    public const string guidDynamicMenuPackageCmdSet = "00000000-0000-0000-0000-00000000";  // get the GUID from the .vsct file
    public const uint cmdidMyCommand = 0x104;
    ```

2. En el archivo *DynamicMenu.cs,* agregue las siguientes directivas using:

    ```csharp
    using EnvDTE;
    using EnvDTE80;
    using System.ComponentModel.Design;
    ```

3. En `DynamicMenu` la clase, agregue un campo privado **dte2**.

    ```csharp
    private DTE2 dte2;
    ```

4. Agregue un campo rootItemId privado:

    ```csharp
    private int rootItemId = 0;
    ```

5. En el DynamicMenu constructor, agregue el comando menu. En la siguiente sección definiremos el `BeforeQueryStatus` controlador de comandos, el controlador de eventos y el predicado de coincidencia.

    ```csharp
    private DynamicMenu(Package package)
    {
        if (package == null)
        {
            throw new ArgumentNullException(nameof(package));
        }

        this.package = package;

        OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;
        if (commandService != null)
        {
            // Add the DynamicItemMenuCommand for the expansion of the root item into N items at run time.
            CommandID dynamicItemRootId = new CommandID(new Guid(DynamicMenuPackageGuids.guidDynamicMenuPackageCmdSet), (int)DynamicMenuPackageGuids.cmdidMyCommand);
            DynamicItemMenuCommand dynamicMenuCommand = new DynamicItemMenuCommand(dynamicItemRootId,
                IsValidDynamicItem,
                OnInvokedDynamicItem,
                OnBeforeQueryStatusDynamicItem);
                commandService.AddCommand(dynamicMenuCommand);
                }

        dte2 = (DTE2)this.ServiceProvider.GetService(typeof(DTE));
    }
    ```

## <a name="implement-the-handlers"></a>Implementar los controladores
 Para implementar elementos de menú dinámicos en un controlador de menú, debe controlar el comando cuando se hace clic en un elemento dinámico. También debe implementar la lógica que establece el estado del elemento de menú. Agregue los controladores `DynamicMenu` a la clase.

1. Para implementar el comando Establecer proyecto de **inicio,** agregue el controlador de eventos **OnInvokedDynamicItem.** Busca el proyecto cuyo nombre es el mismo que el texto del comando que se ha invocado y <xref:EnvDTE.SolutionBuild.StartupProjects%2A> lo establece como el proyecto de inicio estableciendo su ruta de acceso absoluta en la propiedad.

    ```csharp
    private void OnInvokedDynamicItem(object sender, EventArgs args)
    {
        DynamicItemMenuCommand invokedCommand = (DynamicItemMenuCommand)sender;
        // If the command is already checked, we don't need to do anything
        if (invokedCommand.Checked)
            return;

        // Find the project that corresponds to the command text and set it as the startup project
        var projects = dte2.Solution.Projects;
        foreach (Project proj in projects)
        {
            if (invokedCommand.Text.Equals(proj.Name))
            {
                dte2.Solution.SolutionBuild.StartupProjects = proj.FullName;
                return;
            }
        }
    }
    ```

2. Agregue `OnBeforeQueryStatusDynamicItem` el controlador de eventos. Este es el controlador `QueryStatus` al que se llama antes de un evento. Determina si el elemento de menú es un elemento "real", es decir, no el elemento de marcador de posición, y si el elemento ya está comprobado (lo que significa que el proyecto ya está establecido como el proyecto de inicio).

    ```csharp
    private void OnBeforeQueryStatusDynamicItem(object sender, EventArgs args)
    {
        DynamicItemMenuCommand matchedCommand = (DynamicItemMenuCommand)sender;
        matchedCommand.Enabled = true;
        matchedCommand.Visible = true;

        // Find out whether the command ID is 0, which is the ID of the root item.
        // If it is the root item, it matches the constructed DynamicItemMenuCommand,
         // and IsValidDynamicItem won't be called.
        bool isRootItem = (matchedCommand.MatchedCommandId == 0);

        // The index is set to 1 rather than 0 because the Solution.Projects collection is 1-based.
        int indexForDisplay = (isRootItem ? 1 : (matchedCommand.MatchedCommandId - (int) DynamicMenuPackageGuids.cmdidMyCommand) + 1);

        matchedCommand.Text = dte2.Solution.Projects.Item(indexForDisplay).Name;

        Array startupProjects = (Array)dte2.Solution.SolutionBuild.StartupProjects;
        string startupProject = System.IO.Path.GetFileNameWithoutExtension((string)startupProjects.GetValue(0));

        // Check the command if it isn't checked already selected
        matchedCommand.Checked = (matchedCommand.Text == startupProject);

        // Clear the ID because we are done with this item.
        matchedCommand.MatchedCommandId = 0;
    }
    ```

## <a name="implement-the-command-id-match-predicate"></a>Implemente el predicado de coincidencia de identificador de comando

Ahora implemente el predicado de coincidencia. Necesitamos determinar dos cosas: en primer lugar, si el identificador de comando es válido (es mayor o igual que el identificador de comando declarado) y, en segundo lugar, si especifica un proyecto posible (es menor que el número de proyectos de la solución).

```csharp
private bool IsValidDynamicItem(int commandId)
{
    // The match is valid if the command ID is >= the id of our root dynamic start item
    // and the command ID minus the ID of our root dynamic start item
    // is less than or equal to the number of projects in the solution.
    return (commandId >= (int)DynamicMenuPackageGuids.cmdidMyCommand) && ((commandId - (int)DynamicMenuPackageGuids.cmdidMyCommand) < dte2.Solution.Projects.Count);
}
```

## <a name="set-the-vspackage-to-load-only-when-a-solution-has-multiple-projects"></a>Establezca el VSPackage para cargar solo cuando una solución tiene varios proyectos
 Dado que el **comando Establecer proyecto** de inicio no tiene sentido a menos que la solución activa tenga más de un proyecto, puede establecer el VSPackage para que se cargue automáticamente solo en ese caso. Se <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> usa junto con <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids.SolutionHasMultipleProjects>el contexto de la interfaz de usuario. En el archivo *DynamicMenuPackage.cs* agregue los siguientes atributos a la clase DynamicMenuPackage:

```csharp
[PackageRegistration(UseManagedResourcesOnly = true)]
[InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)]
[ProvideMenuResource("Menus.ctmenu", 1)]
[ProvideAutoLoad(UIContextGuids.SolutionHasMultipleProjects)]
[Guid(DynamicMenuPackage.PackageGuidString)]
public sealed class DynamicMenuItemsPackage : Package
{}
```

## <a name="test-the-set-startup-project-command"></a>Pruebe el comando set startup project
 Ahora puede probar el código.

1. Compile la solución y comience la depuración. Debería aparecer la instancia experimental.

2. En la instancia experimental, abra una solución que tenga más de un proyecto.

     Debería ver el icono de flecha en la barra de herramientas del Explorador de **soluciones.** Al expandirlo, deben aparecer elementos de menú que representan los diferentes proyectos de la solución.

3. Al comprobar uno de los proyectos, se convierte en el proyecto de inicio.

4. Al cerrar la solución o abrir una solución que solo tiene un proyecto, el icono de la barra de herramientas debe desaparecer.

## <a name="see-also"></a>Vea también
- [Comandos, menús y barras de herramientas](../extensibility/internals/commands-menus-and-toolbars.md)
- [Cómo VSPackages agregan elementos de interfaz de usuario](../extensibility/internals/how-vspackages-add-user-interface-elements.md)
