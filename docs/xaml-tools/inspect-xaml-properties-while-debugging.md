---
title: Inspeccionar las propiedades XAML durante la depuración | Microsoft Docs
ms.date: 11/12/2019
ms.topic: how-to
ms.assetid: 390edde4-7b8d-4c89-8d69-55106b7e6b11
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- uwp
ms.openlocfilehash: 1c8ac187f5602d1c422fe5699d36deee70341b0f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "85331077"
---
# <a name="inspect-xaml-properties-while-debugging"></a>Inspeccionar las propiedades XAML durante la depuración

Puede obtener una vista en tiempo real del código XAML en ejecución con **Árbol visual dinámico** y **Live Property Explorer**. Estas herramientas le proporcionan una vista de árbol de los elementos de interfaz de usuario de la aplicación XAML en ejecución y le muestran las propiedades en tiempo de ejecución de cualquier elemento de interfaz de usuario que seleccione.

Puede usar estas herramientas en las siguientes configuraciones:

|Tipo de aplicación|Sistema operativo y herramientas|
|-----------------|--------------------------------|
|Aplicaciones de Windows Presentation Foundation (4.0 y versiones posteriores)|Windows 7 y versiones posteriores|
|Aplicaciones universales de Windows|Windows 10 y versiones posteriores, con el [SDK de Windows 10](https://dev.windows.com/downloads/windows-10-sdk)|

## <a name="look-at-elements-in-the-live-visual-tree"></a>Buscar elementos en el árbol visual dinámico

Comencemos con una aplicación WPF muy sencilla que tiene una vista de lista y un botón. Al hacer clic en el botón, se agrega otro elemento a la lista. Los elementos con números pares se muestran en color gris, mientras que los elementos con números impares se muestran de color amarillo.

### <a name="create-the-project"></a>Crear el proyecto

1. Cree una nueva aplicación WPF de c# (**archivo**  >  **nuevo**  >  **proyecto**, escriba "WPF de c#" y elija **aplicación WPF (.net Core)** o **aplicación WPF (.NET Framework)**). Asígnele el nombre **TestXAML**.

1. Cambie el archivo MainWindow.xaml por lo siguiente:

   ```xaml
   <Window x:Class="TestXAML.MainWindow"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
      xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
      xmlns:local="clr-namespace:TestXAML"
      mc:Ignorable="d"
      Title="MainWindow" Height="350" Width="525">
      <Grid>
         <Button x:Name="button" Background="LightBlue" Content="Add Item" HorizontalAlignment="Left" Margin="216,206,0,0" VerticalAlignment="Top" Width="75" Click="button_Click"/>
         <ListBox x:Name="listBox" HorizontalAlignment="Left" Height="100" VerticalAlignment="Top" Width="100" Margin="205,80,0,0"/>
      </Grid>
   </Window>
   ```

1. Agregue el siguiente controlador de comandos al archivo MainWindow.xaml.cs:

   ```csharp
   int count;

   private void button_Click(object sender, RoutedEventArgs e)
   {
      ListBoxItem item = new ListBoxItem();
      item.Content = "Item" + ++count;
      if (count % 2 == 0)
      {
         item.Background = Brushes.LightGray;
      }
      else
      {
         item.Background = Brushes.LightYellow;
      }
      listBox.Items.Add(item);
   }
   ```

1. Compile la solución y comience la depuración. La configuración de compilación debe ser Depurar, no Liberar. Para obtener más información sobre las configuraciones de compilación, vea Descripción de las [configuraciones de compilación](../ide/understanding-build-configurations.md)).

   Cuando aparezca la ventana, debería ver que la barra de herramientas de la aplicación aparece dentro de la aplicación en ejecución.

   ::: moniker range=">= vs-2019"
   ![Ventana principal de la aplicación](../debugger/media/vs-2019/livevisualtree-app.png "LiveVIsualTree: aplicación")
   ::: moniker-end
   ::: moniker range="vs-2017"
   ![Ventana principal de la aplicación](../debugger/media/livevisualtree-app.png "LiveVIsualTree: aplicación")
   ::: moniker-end

1. Ahora, haga clic en el botón **Agregar elemento** varias veces para agregar nuevos elementos a la lista.

### <a name="inspect-xaml-properties"></a>Inspección de propiedades XAML

1. A continuación, abra la ventana del **árbol visual activo** haciendo clic en el botón de la izquierda de la barra de herramientas en la aplicación (o vaya a **depurar > árbol Visual de Windows > Live**). Una vez abierta, arrástrela fuera de su posición de acoplamiento para que podamos ver esta ventana y la ventana **propiedades dinámicas** en paralelo.

1. En la ventana **Árbol visual dinámico**, expanda el nodo **ContentPresenter**. Debe contener nodos para el botón y el cuadro de lista. Expanda el cuadro de lista (y luego **ScrollContentPresenter** e **ItemsPresenter**) para buscar los elementos del cuadro de lista.

   ::: moniker range=">= vs-2019"
   Si no ve el nodo **ContentPresenter** , alterne el icono **Mostrar solo mi XAML** en la barra de herramientas. A partir de la versión 16,4 de Visual Studio 2019, la vista de los elementos XAML se simplifica de forma predeterminada mediante la característica solo mi XAML. También puede [deshabilitar esta opción](../debugger/general-debugging-options-dialog-box.md) en opciones para mostrar siempre todos los elementos XAML.
   ::: moniker-end

   La ventana debe ser similar a la que se muestra a continuación:

   ::: moniker range=">= vs-2019"
   ![ListBoxItems en el Árbol visual dinámico](../debugger/media/vs-2019/livevisualtree-listboxitems.png "LiveVisualTree-elementos ListBoxItem")
   ::: moniker-end
   ::: moniker range="vs-2017"
   ![ListBoxItems en el Árbol visual dinámico](../debugger/media/livevisualtree-listboxitems.png "LiveVisualTree-elementos ListBoxItem")
   ::: moniker-end

1. Vuelva a la ventana de la aplicación y agregue algunos elementos más. Debería ver más elementos del cuadro de lista en **Live Visual Tree**.

1. Ahora, echemos un vistazo a las propiedades de uno de los elementos del cuadro de lista.

   Seleccione el primer elemento del cuadro de lista de **Live Visual Tree** y haga clic en el icono **Mostrar propiedades** de la barra de herramientas. Debería aparecer **Live Property Explorer**. Tenga en cuenta que el campo de **contenido** es "Item1" y el campo de color de **fondo**  >  **Color** es **#FFFFFFE0**.

1. Vuelva a **Live Visual Tree** y seleccione el segundo elemento del cuadro de lista. El **Explorador de propiedades activo** debe mostrar que el campo de **contenido** es "Item2" y el campo de color de **fondo**  >  **Color** es **#FFD3D3D3** (dependiendo del tema).

   > [!NOTE]
   > Un borde amarillo alrededor de una propiedad en el **Explorador de propiedades activo** significa que el valor de la propiedad se establece a través de un enlace, como `Color = {BindingExpression}` . Un borde verde significa que el valor se establece mediante un recurso, como `Color = {StaticResource MyBrush}` .

   La estructura real del XAML tiene muchos elementos que probablemente no le interesen, y si no conoce bien el código tal vez tenga que perder bastante tiempo navegando por el árbol para encontrar lo que está buscando. **Live Visual Tree** tiene un par de maneras que le permiten usar la interfaz de usuario de la aplicación para poder encontrar el elemento que desea examinar.

   ::: moniker range=">= vs-2019"
   **Seleccione el elemento en la aplicación en ejecución**. Puede habilitar este modo al seleccionar el botón situado más a la izquierda de la barra de herramientas de **Live Visual Tree**. Con este modo activado puede seleccionar un elemento de interfaz de usuario en la aplicación; **Live Visual Tree** (y **Live Property Viewer**) se actualiza automáticamente para mostrar el nodo en el árbol correspondiente a dicho elemento y sus propiedades. A partir de la versión 16,4 de Visual Studio 2019, puede [configurar el comportamiento de la selección de elementos](../debugger/general-debugging-options-dialog-box.md).

   **Mostrar adornos de diseño en la aplicación en ejecución**. Puede habilitar este modo al seleccionar el botón que está justo a la derecha del botón Habilitar selección. Cuando la opción **Mostrar adornos de diseño** está activada, la ventana de la aplicación muestra líneas horizontales y verticales a lo largo de los límites del objeto seleccionado para que pueda ver lo que alinea, así como rectángulos que muestran los márgenes. Por ejemplo, active la **opción Seleccionar elemento** y **Mostrar diseño** en y seleccione el bloque de texto **Agregar elemento** en la aplicación. Debería ver el nodo del bloque de texto en **Live Visual Tree** y las propiedades del bloque de texto en **Live Property Viewer**, así como las líneas horizontales y verticales en los límites del bloque de texto.

   ![LivePropertyViewer en DisplayLayout](../debugger/media/vs-2019/livevisualtreelivepropertyviewer-displaylayout.png "LiveVisualTreeLivePropertyViewer-DisplayLayout")

   **Obtener una vista previa de la selección**. Puede habilitar este modo seleccionando el tercer botón de la izquierda en la barra de herramientas de Live Visual Tree. Este modo muestra el XAML donde se ha declarado el elemento, siempre y cuando tenga acceso al código fuente de la aplicación. Seleccione **Seleccionar elemento** y **vista previa**y, a continuación, seleccione el botón en nuestra aplicación de prueba. Se abre el archivo MainWindow.xaml en Visual Studio y se coloca el cursor en la línea en la que se define el botón.
   ::: moniker-end

   ::: moniker range="vs-2017"
   **Habilitar la selección en la aplicación en ejecución**. Puede habilitar este modo al seleccionar el botón situado más a la izquierda de la barra de herramientas de **Live Visual Tree**. Con este modo activado puede seleccionar un elemento de interfaz de usuario en la aplicación; **Live Visual Tree** (y **Live Property Viewer**) se actualiza automáticamente para mostrar el nodo en el árbol correspondiente a dicho elemento y sus propiedades.

   **Mostrar adornos de diseño en la aplicación en ejecución**. Puede habilitar este modo al seleccionar el botón que está justo a la derecha del botón Habilitar selección. Cuando la opción **Mostrar adornos de diseño** está activada, la ventana de la aplicación muestra líneas horizontales y verticales a lo largo de los límites del objeto seleccionado para que pueda ver lo que alinea, así como rectángulos que muestran los márgenes. Por ejemplo, active **Habilitar selección** y **Mostrar diseño**, y seleccione el bloque de texto **Agregar elemento** en la aplicación. Debería ver el nodo del bloque de texto en **Live Visual Tree** y las propiedades del bloque de texto en **Live Property Viewer**, así como las líneas horizontales y verticales en los límites del bloque de texto.

   ![LivePropertyViewer en DisplayLayout](../debugger/media/livevisualtreelivepropertyviewer-displaylayout.png "LiveVisualTreeLivePropertyViewer-DisplayLayout")

   **Obtener una vista previa de la selección**. Puede habilitar este modo seleccionando el tercer botón de la izquierda en la barra de herramientas de Live Visual Tree. Este modo muestra el XAML donde se ha declarado el elemento, siempre y cuando tenga acceso al código fuente de la aplicación. Seleccione **Habilitar selección** y **Obtener una vista previa de la selección** y, luego, seleccione el botón de nuestra aplicación de prueba. Se abre el archivo MainWindow.xaml en Visual Studio y se coloca el cursor en la línea en la que se define el botón.
   ::: moniker-end

## <a name="use-xaml-tools-with-running-applications"></a>Usar herramientas XAML con aplicaciones en ejecución

Puede usar estas herramientas XAML, aunque no disponga del código fuente. Al adjuntar a una aplicación XAML en ejecución, también puede usar **Live Visual Tree** en los elementos de interfaz de usuario de la aplicación. Esto es un ejemplo, en el que se ha usado la misma aplicación de prueba WPF que hemos usado antes.

1. Inicie la aplicación **TestXaml** en la configuración Liberar. No puede adjuntar a un proceso que se está ejecutando en una configuración **Depurar**.

2. Abra una segunda instancia de Visual Studio y haga clic en **Depurar > Adjuntar al proceso**. Busque **TestXaml.exe** en la lista de procesos disponibles y haga clic en **Adjuntar**.

3. La aplicación comienza a ejecutarse.

4. En la segunda instancia de Visual Studio, abra **Live Visual Tree** (**Depurar > Ventanas > Live Visual Tree**). Debería ver los elementos de interfaz de usuario **TestXaml** y debería poder manipularlos como lo hizo al depurar directamente la aplicación.

## <a name="see-also"></a>Vea también

[Escribir y depurar código XAML en ejecución con recarga activa de XAML](xaml-hot-reload.md)
