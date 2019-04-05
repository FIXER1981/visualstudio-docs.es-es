---
title: Filtrar Generar plantillas desde otras plantillas mediante secuencias de Escape | Documentos de Microsoft
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- text templates, generating templates from templates
ms.assetid: 4126156a-7cea-48b8-925e-7790806cfe6c
caps.latest.revision: 37
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: a710554d46df8238f33aa90b647def337b57a9a3
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "58987105"
---
# <a name="how-to-generate-templates-from-templates-by-using-escape-sequences"></a>Filtrar Generar plantillas desde otras plantillas mediante secuencias de escape
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Puede crear una plantilla de texto que se crea otra plantilla de texto como salida de texto generada. Para ello, debe usar las secuencias de escape para delinear las etiquetas de la plantilla de texto. Si no usa secuencias de escape, la plantilla de texto generada tendrá un significado definido previamente. Para obtener más información sobre el uso de secuencias de escape en plantillas de texto, consulte [utilizando las secuencias de Escape en plantillas de texto](../modeling/using-escape-sequences-in-text-templates.md).  
  
### <a name="to-generate-a-text-template-from-within-a-text-template"></a>Para generar una plantilla de texto desde dentro de una plantilla de texto  
  
-   Utilice la barra diagonal inversa (\\) como carácter de escape para producir las etiquetas de marcado necesario dentro de la plantilla de texto para las directivas, instrucciones, expresiones y funciones en un archivo de plantilla de texto independiente de la clase.  
  
    ```  
    \<#@ directive \#>  
    \<# statement \#>  
    \<#= expression \#>  
    \<#+ classfeature \#>  
    ```  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente utiliza caracteres de escape para generar una plantilla de texto desde una plantilla de texto. El `output` Directiva establece el tipo de archivo de destino en el tipo de archivo de plantilla de texto (.tt).  
  
```csharp  
\<#@ output extension=".tt" \#>  
\<#@ assembly name="System.Xml.dll" \#>  
\<#@ import namespace="System.Xml" \#>  
\<#  
XmlDocument xDoc = new XmlDocument();  
//System.Diagnostics.Debugger.Break();  
    xDoc.Load(@"E:\CSharp\Overview.xml");  
    XmlAttributeCollection attributes = xDoc.Attributes;  
    if (attributes != null)  
    {  
       foreach (XmlAttribute attr in attributes)  
       {\#>  
           \<#= attr.Name \#>  
       \<#}  
     }  
\#>  
```  
  
 La salida de texto generado es una plantilla de texto.  
  
```  
<#@ output extension=".tt" #>  
<#@ assembly name="System.Xml.dll" #>  
<#@ import namespace="System.Xml" #>  
<#  
XmlDocument xDoc = new XmlDocument();  
//System.Diagnostics.Debugger.Break();  
    xDoc.Load(@"E:\CSharp\Overview.xml");  
    XmlAttributeCollection attributes = xDoc.Attributes;  
    if (attributes != null)  
    {  
       foreach (XmlAttribute attr in attributes)  
       {#>  
           <#= attr.Name #>  
       <#}  
     }  
#>  
```
