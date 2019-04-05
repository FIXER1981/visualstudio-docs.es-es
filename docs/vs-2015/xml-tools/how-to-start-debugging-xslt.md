---
title: Filtrar Iniciar la depuración XSLT | Documentos de Microsoft
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 8358335a-fcb0-45e0-a37e-45b43e49ec0a
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 2a7553bb07e90e690d6409a2ad22636ddc8b627c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "58994942"
---
# <a name="how-to-start-debugging-xslt"></a>Filtrar Comenzar a depurar XSLT
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

El depurador de XSLT se puede utilizar para depurar una hoja de estilos XSLT o una aplicación XSLT. Durante la depuración, puede ejecutar código de línea en línea yendo al código, recorriéndolo o saliendo de él. Los comandos para utilizar la funcionalidad de paso de código en el depurador de XSLT son los mismos que en los demás depuradores de Visual Studio. Una vez se haya iniciado la depuración, el depurador XSLT abre unas ventanas para mostrar el documento de entrada y la salida XSLT.  
  
## <a name="xml-editor"></a>Editor XML  
 Se puede iniciar el depurador desde el Editor XML. Esto le permite depurar mientras diseña la hoja de estilos.  
  
#### <a name="to-start-debugging-from-a-style-sheet"></a>Para iniciar la depuración desde una hoja de estilos  
  
1.  Abra la hoja de estilos en el Editor XML.  
  
2.  Seleccione **Depurar XSL** desde el **XML** menú.  
  
#### <a name="to-start-debugging-from-an-xml-input-document"></a>Para iniciar la depuración desde un documento de entrada XML  
  
1.  Abra el documento XML en el Editor XML.  
  
2.  Seleccione **Depurar XSL** desde el **XML** menú.  
  
## <a name="xslt-from-other-languages"></a>XSLT desde otros lenguajes  
 También puede ir al código XSLT mientras depura una aplicación. Cuando presiona F11 en una llamada <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=fullName>, el depurador puede ir al código XSLT.  
  
> [!NOTE]
>  No se puede ir al código XSLT desde la clase <xref:System.Xml.Xsl.XslTransform>. La clase <xref:System.Xml.Xsl.XslCompiledTransform> es el único procesador XSLT que admite la entrada al código XSLT durante la depuración.  
  
#### <a name="to-start-debugging-an-xslt-application"></a>Para iniciar la depuración de una aplicación XSLT  
  
1.  Al crear una instancia del objeto <xref:System.Xml.Xsl.XslCompiledTransform>, establezca el parámetro `enableDebug` a `true` en el código.  
  
     Esto indica al procesador XSLT que cree información de depuración al compilar el código.  
  
2.  Presione F11 para ir al código XSLT.  
  
     La hoja de estilos XSLT se carga en una nueva ventana de documento y se inicia el depurador de XSLT.  
  
     Como alternativa, puede agregar un punto de interrupción a la hoja de estilos y ejecutar la aplicación.  
  
### <a name="example"></a>Ejemplo  
 A continuación se ofrece un ejemplo de un programa XSLT de C#  que muestra cómo habilitar la depuración de XSLT.  
  
```  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Xsl;  
  
namespace ConsoleApplication   
{  
  class Program   
  {  
    private const string sourceFile = @"c:\data\xsl_files\books.xml";  
    private const string stylesheet = @"c:\data\xsl_files\belowAvg.xsl";  
    private const string outputFile = @"c:\data\xsl_files\output.xml";  
  
    static void Main(string[] args)  
    {  
      // Enable XSLT debugging.  
      XslCompiledTransform xslt = new XslCompiledTransform(true);  
  
      // Compile the style sheet.  
      xslt.Load(stylesheet)  
  
      // Execute the XSLT transform.  
      FileStream outputStream = new FileStream(outputFile, FileMode.Append);  
      xslt.Transform(sourceFile, null, outputStream);  
    }  
  }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Depurar una hoja de estilos XSLT](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)   
 [Información general de ejecución paso a paso el código](http://msdn.microsoft.com/8791dac9-64d1-4bb9-b59e-8d59af1833f9)
