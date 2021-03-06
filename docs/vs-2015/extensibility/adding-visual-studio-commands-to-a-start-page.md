---
title: Agregar comandos de Visual Studio a una página de inicio | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- start page commands
- vs:VSCommands
ms.assetid: a8e2765c-cfb5-47b5-a414-6e48b434e0c2
caps.latest.revision: 21
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0a2042ef9a96eed99636ea0a2f5f09d99cd35ea2
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "65699155"
---
# <a name="adding-visual-studio-commands-to-a-start-page"></a>Adición de comandos de Visual Studio a una página de inicio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Al crear una página de inicio personalizada, puede agregarle comandos de Visual Studio. En este documento se describen las distintas formas de enlazar comandos de Visual Studio a objetos XAML en una página de inicio.  
  
 Para obtener más información sobre los comandos de XAML, vea [información general sobre comandos](https://msdn.microsoft.com/library/bc208dfe-367d-426a-99de-52b7e7511e81) .  
  
## <a name="adding-commands-from-the-command-well"></a>Agregar comandos desde el cuadro de comandos  
 La página de inicio que se crea al [crear una página de inicio personalizada](../extensibility/creating-a-custom-start-page.md) agrega los <xref:Microsoft.VisualStudio.PlatformUI?displayProperty=fullName> espacios de <xref:Microsoft.VisualStudio.Shell?displayProperty=fullName> nombres y, como se indica a continuación.  
  
```  
xmlns:vs="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.14.0"  
xmlns:vsfx="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"  
```  
  
 Agregue otro espacio de nombres para Microsoft. VisualStudio. Shell desde el ensamblado Microsoft.VisualStudio.Shell.Immutable.11.0.dll. (Puede que tenga que agregar una referencia a este ensamblado en el proyecto).  
  
```xml  
xmlns:vscom="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.Immutable.11.0"  
```  
  
 Puede usar el `vscom:` alias para enlazar comandos de Visual Studio a controles XAML en la página estableciendo la <xref:System.Windows.Controls.Primitives.ButtonBase.Command%2A> propiedad del control en `vscom:VSCommands.ExecuteCommand` . Después, puede establecer la <xref:System.Windows.Controls.Primitives.ButtonBase.CommandParameter%2A> propiedad en el nombre del comando que se va a ejecutar, como se muestra en el ejemplo siguiente.  
  
```xml  
<Button Name="btnNewProj" Content="New Project"   
    Command="{x:Static vscom:VSCommands.ExecuteCommand}"  
    CommandParameter="File.NewProject" >  
</Button>  
```  
  
> [!NOTE]
> El `x:` alias, que hace referencia al esquema XAML, es necesario al principio de todos los comandos.  
  
 Puede establecer el valor de la `Command` propiedad en cualquier comando al que se pueda tener acceso desde la ventana de **comandos** . Para obtener una lista de los comandos disponibles, vea [alias de comandos de Visual Studio](../ide/reference/visual-studio-command-aliases.md).  
  
 Si el comando que se va a agregar requiere un parámetro adicional, puede agregarlo al valor de la `CommandParameter` propiedad. Separe los parámetros de los comandos mediante espacios, tal como se muestra en el ejemplo siguiente.  
  
```xml  
<Button Content="Web Search"   
        Command="{x:Static vscom:VSCommands.ExecuteCommand}"  
        CommandParameter="View.WebBrowser www.bing.com" />  
```  
  
### <a name="calling-extensions-from-the-command-well"></a>Llamar a extensiones desde el comando  
 Puede llamar a comandos desde VSPackages registrados mediante la misma sintaxis que se usa para llamar a otros comandos de Visual Studio. Por ejemplo, si un VSPackage instalado agrega un comando de **Página principal** al menú **Ver** , puede llamar a ese comando estableciendo `CommandParameter` en `View.HomePage` .  
  
> [!NOTE]
> Si llama a un comando que está asociado a un VSPackage, el paquete se debe cargar cuando se invoca el comando.  
  
## <a name="adding-commands-from-assemblies"></a>Agregar comandos desde ensamblados  
 Para llamar a un comando desde un ensamblado o para tener acceso al código de un VSPackage que no está asociado a un comando de menú, debe crear un alias para el ensamblado y, a continuación, llamar al alias.  
  
#### <a name="to-call-a-command-from-an-assembly"></a>Para llamar a un comando desde un ensamblado  
  
1. En la solución, agregue una referencia al ensamblado.  
  
2. En la parte superior del archivo StartPage. XAML, agregue una directiva de espacio de nombres para el ensamblado, tal y como se muestra en el ejemplo siguiente.  
  
    ```xml  
    xmlns:vsc="clr-namespace:WebUserControl;assembly=WebUserControl"  
    ```  
  
3. Para invocar el comando, establezca la `Command` propiedad de un objeto XAML, tal y como se muestra en el ejemplo siguiente.  
  
     Lenguaje  
  
    ```  
    <vs:Button Text="Hide me" Command="{x:Static vsc:HideControl}" .../>  
    ```  
  
> [!NOTE]
> Debe copiar el ensamblado y, a continuación, pegarlo en. \\ *Carpeta de instalación de Visual Studio*\Common7\IDE\PrivateAssemblies\ para asegurarse de que se carga antes de que se llame a.  
  
## <a name="adding-commands-with-the-dte-object"></a>Agregar comandos con el objeto DTE  
 Puede tener acceso al objeto DTE desde una página de inicio, tanto en el marcado como en el código.  
  
 En el marcado, puede acceder a él mediante la sintaxis de la [extensión de marcado de enlace](https://msdn.microsoft.com/library/83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63) para llamar al <xref:EnvDTE.DTE> objeto. Puede usar este enfoque para enlazar a propiedades simples como las que devuelven colecciones, pero no puede enlazar a métodos o servicios. En el ejemplo siguiente se muestra un <xref:System.Windows.Controls.TextBlock> control que se enlaza a la <xref:EnvDTE._DTE.Name%2A> propiedad y un <xref:System.Windows.Controls.ListBox> control que enumera las <xref:EnvDTE.Window.Caption%2A> propiedades de la colección devuelta por la <xref:EnvDTE._DTE.Windows%2A> propiedad.  
  
```xml  
<TextBlock Text="{Binding Path=DTE.Name}" FontSize="12" HorizontalAlignment="Center"/>  
<ListBox ItemsSource="{Binding Path=DTE.Windows}">  
    <ListBox.ItemTemplate>  
        <DataTemplate>  
            <TextBlock Text="{Binding Path=Caption}"/>  
        </DataTemplate>  
    </ListBox.ItemTemplate>  
</ListBox  
```  
  
 Para obtener un ejemplo, vea [Tutorial: guardar la configuración de usuario en una página de inicio](../extensibility/walkthrough-saving-user-settings-on-a-start-page.md).  
  
## <a name="see-also"></a>Consulte también  
 [Adición de control de usuario a la página de inicio](../extensibility/adding-user-control-to-the-start-page.md)
