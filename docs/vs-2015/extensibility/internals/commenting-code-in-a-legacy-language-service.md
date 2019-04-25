---
title: Comentario de código en un servicio de lenguaje heredado | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- comments, supporting in language services [managed package framework]
- language services [managed package framework], commenting code
ms.assetid: 9600d6f0-e2b6-4fe0-b935-fb32affb97a4
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: cd1405456ca9a6ba00926c82bcc7959ea36d26c2
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "58988605"
---
# <a name="commenting-code-in-a-legacy-language-service"></a>Comentario de código en un servicio de lenguaje heredado
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Normalmente, los lenguajes de programación proporcionan un medio para anotar o comentar el código. Un comentario es una sección de texto que proporciona información adicional sobre el código, pero se omite durante la compilación o interpretación.  
  
 Las clases de framework (MPF) de paquetes administrados proporcionan compatibilidad para comentar y quitar comentario de texto seleccionado.  
  
## <a name="comment-styles"></a>Estilos de comentario  
 Hay dos estilos generales del comentario:  
  
1. Comentarios en línea, donde es el comentario en una sola línea.  
  
2. Comentarios del bloque, donde el comentario puede incluir varias líneas.  
  
   Comentarios de línea suelen tengan un carácter inicial (o caracteres), mientras que los comentarios del bloque tiene los caracteres inicial y final. Por ejemplo, en C#, un comentario de línea empieza con / /, y un comentario de bloque comienza con / * y termina con \*/.  
  
   Cuando el usuario selecciona el comando **selección con comentarios** desde el **editar** -> **avanzadas** el comando de menú, se enruta a la <xref:Microsoft.VisualStudio.Package.Source.CommentSpan%2A> método en el <xref:Microsoft.VisualStudio.Package.Source> clase. Cuando el usuario selecciona el comando **selección sin comentarios**, el comando se enruta a la <xref:Microsoft.VisualStudio.Package.Source.UncommentSpan%2A> método.  
  
## <a name="supporting-code-comments"></a>Comentarios del código auxiliar  
 Puede tener los comentarios del código de lenguaje servicio soporte técnico por medio de la `EnableCommenting` con el nombre de parámetro de la <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> . Esto establece la <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCommenting%2A> propiedad de la <xref:Microsoft.VisualStudio.Package.LanguagePreferences> clase. Para obtener más información sobre la configuración de idioma servicce características, consulte [registrar un servicio de lenguaje heredado](../../extensibility/internals/registering-a-legacy-language-service1.md)).  
  
 También debe invalidar el <xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A> método devuelva un <xref:Microsoft.VisualStudio.Package.CommentInfo> estructura con los caracteres de comentario para su idioma. C#-caracteres de comentario de línea de estilo son el valor predeterminado.  
  
### <a name="example"></a>Ejemplo  
 Este es un ejemplo de implementación de la <xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A> método.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
  
namespace MyLanguagePackage  
{  
    class MySource : Source  
    {  
        public override CommentInfo GetCommentFormat() {  
            CommentInfo info = new CommentInfo();  
            info.LineStart       = "//";  
            info.BlockStart      = "/*";  
            info.BlockEnd        = "*/";  
            info.UseLineComments = true;  
            return info;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Características del servicio de lenguaje heredado](../../extensibility/internals/legacy-language-service-features1.md)   
 [Registro de un servicio de lenguaje heredado](../../extensibility/internals/registering-a-legacy-language-service1.md)
