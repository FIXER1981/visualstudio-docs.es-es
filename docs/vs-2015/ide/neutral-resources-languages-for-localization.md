---
title: Idiomas de los recursos neutros para la localización | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- localization [Visual Studio], resources
- NeutralResourcesLanguageAttribute class
- globalization [Visual Studio], resources
- resources [Visual Studio], fallback system
- culture, locating resources
- neutral resources
ms.assetid: ef064995-3b84-4698-a708-9689b7723533
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: da39ed9373daaa1dbef21ad36931ce97ea1f1e1b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62558273"
---
# <a name="neutral-resources-languages-for-localization"></a>Idiomas de los recursos neutros para la localización
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La clase <xref:System.Resources.NeutralResourcesLanguageAttribute> especifica la referencia cultural de los recursos incluidos en el ensamblado principal. Este atributo se usa para mejorar el rendimiento, de forma que el objeto <xref:System.Resources.ResourceManager> no busque los recursos que se incluyen en el ensamblado principal.  
  
 El código siguiente muestra cómo establecer el idioma de los recursos neutros. El código se puede colocar en un script de compilación o en el archivo AssemblyInfo.vb o AssemblyInfo.cs.  
  
```vb  
' Set neutral resources language for assembly.  
<Assembly: NeutralResourcesLanguageAttribute("en")>  
  
```  
  
```csharp  
// Set neutral resources language for assembly.  
[assembly: NeutralResourcesLanguageAttribute("en")]  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Resources.ResourceManager>   
 [Introducción a aplicaciones internacionales basadas en .NET Framework](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)   
 [Organización jerárquica de recursos para la localización](../ide/hierarchical-organization-of-resources-for-localization.md)   
 [Localizar aplicaciones](../ide/localizing-applications.md)   
 [Globalizar y localizar aplicaciones](../ide/globalizing-and-localizing-applications.md)
