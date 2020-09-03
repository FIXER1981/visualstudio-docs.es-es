---
title: 'Cómo: Distribuir fragmentos de código | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code snippets, distributing
ms.assetid: 5f717abd-e167-47ae-818c-6b0bae100ceb
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e1a692ee29ea9d43e1a0a4fbed5c52934d69256d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "77476983"
---
# <a name="how-to-distribute-code-snippets"></a>Cómo: Distribuir fragmentos de código
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Los fragmentos de código se pueden entregar directamente a los compañeros para que los instalen en sus equipos mediante el Administrador de fragmentos de código. No obstante, si tiene que distribuir varios fragmentos de código o le gustaría distribuirlos más ampliamente, incluya el archivo de fragmento de código en una extensión de Visual Studio que puedan instalar los usuarios de esta solución.

 Debe instalar el SDK de Visual Studio para poder crear extensiones de Visual Studio. Busque la versión de VSSDK que coincida con la instalación de Visual Studio en [descargas de Visual studio 2015](https://visualstudio.microsoft.com/vs/older-downloads/).

## <a name="setting-up-the-extension"></a>Configura la extensión
 En este procedimiento se usará el mismo fragmento de código Hello World creado en [Tutorial: Crear un fragmento de código](../ide/walkthrough-creating-a-code-snippet.md). Nosotros le proporcionaremos el texto .snippet para que no tenga que volver a crearlo.

1. Cree un nuevo proyecto de VSIX denominado **TestSnippet**. (**Archivo/Nuevo/Proyecto/Visual C# (o Visual Basic/Extensibilidad**)

2. En el proyecto **TestSnippet**, agregue un nuevo archivo XML con el nombre **VBCodeSnippet.snippet**. Reemplace el contenido por lo siguiente:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <CodeSnippets
        xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
      <CodeSnippet Format="1.0.0">
        <Header>
          <Title>Hello World VB</Title>
          <Shortcut>HelloWorld</Shortcut>
          <Description>Inserts code</Description>
          <Author>MSIT</Author>
          <SnippetTypes>
            <SnippetType>Expansion</SnippetType>
            <SnippetType>SurroundsWith</SnippetType>
          </SnippetTypes>
        </Header>
        <Snippet>
          <Code Language="VB">
            <![CDATA[Console.WriteLine("Hello, World!")]]>
          </Code>
        </Snippet>
      </CodeSnippet>
    </CodeSnippets>
    ```

#### <a name="setting-up-the-directory-structure"></a>Configurar la estructura de directorios

1. En el Explorador de soluciones, seleccione el nodo del proyecto y agregue una carpeta que tenga el mismo nombre que desea para el fragmento de código en el Administrador de fragmentos de código. En este caso, debe ser **HelloWorldVB**.

2. Mueva el archivo .snippet a la carpeta **HelloWorldVB**.

3. Seleccione el archivo. snippet en el Explorador de soluciones y, en la ventana **propiedades** , asegúrese de que **acción de compilación** está establecido en **contenido**, **Copiar en el directorio de salida** está establecido en **copiar siempre**e **incluir en VSIX** está establecido en **true**.

#### <a name="adding-the-pkgdef-file"></a>Agregar el archivo .pkgdef

1. Agregue un archivo de texto a la carpeta **HelloWorldVB** y asígnele el nombre **HelloWorldVB.pkgdef**. Este archivo se usa para agregar determinadas claves al registro. En este caso se agrega una nueva clave a

     **HKCU\Software\Microsoft\VisualStudio\14.0\Languages\CodeExpansions\Basic**.

2. Agregue las líneas siguientes al archivo.

    ```
    // Visual Basic
    [$RootKey$\Languages\CodeExpansions\Basic\Paths]
    "HelloWorldVB"="$PackageFolder$"
    ```

     Si examina esta clave, puede ver cómo especificar diferentes lenguajes.

3. Seleccione el archivo. pkgdef en el Explorador de soluciones y, en la ventana **propiedades** , asegúrese de que **acción de compilación** está establecido en **contenido**, **Copiar en el directorio de salida** está establecido en **copiar siempre**e **incluir en VSIX** está establecido en **true**.

4. Agregue el archivo .pkgdef como activo en el manifiesto de VSIX. En el archivo source.extension.vsixmanifest, vaya a la pestaña **Activos** y haga clic en **Nuevo**.

5. En el cuadro de diálogo **Agregar nuevo activo**, establezca **Tipo** en **Microsoft.VisualStudio.VsPackage**, **Tipo** en **Archivo en filesystem** y **Ruta de acceso** en **HelloWorldVB.pkgdef** (debe aparecer en la lista desplegable).

### <a name="testing-the-snippet"></a>Probar el fragmento de código

1. Ahora hay que asegurarse de que el fragmento de código funciona en la instancia experimental de Visual Studio. La instancia experimental es una segunda copia de Visual Studio que es independiente de la que se emplea para escribir código. Permite trabajar en una extensión sin que el entorno de desarrollo se vea afectado.

2. Compile la solución y comience la depuración. Aparece una segunda instancia de Visual Studio.

3. En la instancia experimental, vaya a **herramientas/administrador de fragmentos de código** y establezca el **idioma** en **básico**. Verá que HelloWorldVB es una de las carpetas y podrá expandirla para ver el fragmento de código HelloWorldVB.

4. Pruebe el fragmento de código. En la instancia experimental, abra un proyecto de Visual Basic y luego abra uno de los archivos de código. Coloque el cursor en algún lugar del código, haga clic con el botón derecho y, en el menú contextual, seleccione **Insertar fragmento de código**.

5. Verá que una de las carpetas es HelloWorldVB. Haga doble clic en ella. Debería ver un elemento emergente **Insertar fragmento de código: HellowWorldVB >** con una lista desplegable **HelloWorldVB**. Haga clic en la lista desplegable de HelloWorldVB. Verá la línea siguiente agregada al archivo:

    ```vb
    Console.WriteLine("Hello, World!")
    ```

## <a name="see-also"></a>Consulte también
 [Fragmentos de código](../ide/code-snippets.md)
