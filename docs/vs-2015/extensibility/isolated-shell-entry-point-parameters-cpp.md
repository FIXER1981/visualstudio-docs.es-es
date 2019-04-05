---
title: Aislamiento de los parámetros de punto de entrada de Shell (C++) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Shell [Visual Studio], isolated mode%2C Start entry point
- Visual Studio shell, isolated mode%2C Start entry point
ms.assetid: 18f4b18b-2173-4afa-ba0a-42fe33e61118
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 313632661c3f73fdbd0f23616a068913c77508f8
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "58999689"
---
# <a name="isolated-shell-entry-point-parameters-c"></a>Parámetros de punto de entrada de Shell aislado (C++)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cuando se inicia una aplicación basada en el shell de Visual Studio, llama el punto de entrada de inicio de Visual Studio shell. La siguiente configuración puede invalidarse en la llamada al punto de entrada de inicio del shell. Para obtener una descripción de cada configuración, vea [. Archivos pkgdef](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md).  
  
- AddinsAllowed  
  
- AllowsDroppedFilesOnMainWindow  
  
- AppName  
  
- CommandLineLogo  
  
- DefaultHomePage  
  
- DefaultProjectsLocation  
  
- DefaultSearchPage  
  
- DefaultUserFilesFolderRoot  
  
- DisableOutputWindow  
  
- HideMiscellaneousFilesByDefault  
  
- HideSolutionConcept  
  
- NewProjDlgInstalledTemplatesHdr  
  
- NewProjDlgSlnTreeNodeTitle  
  
- SolutionFileCreatorIdentifier  
  
- SolutionFileExt  
  
- UserFilesSubFolderName  
  
- UserOptsFileExt  
  
  La plantilla de Visual Studio Shell aislado crea un archivo de código fuente, *solutionName*.cpp, donde *solutionName* es el nombre de la solución para la aplicación. Este archivo define el punto de entrada principal para la aplicación, la función _tWinMain. Esta función invoca el punto de entrada de inicio del shell.  
  
  Puede cambiar el comportamiento de la aplicación al cambiar esta configuración cuando se inicia la aplicación.  
  
## <a name="parameters"></a>Parámetros  
 El punto de entrada de inicio del shell de Visual Studio define cinco parámetros. No cambie los cuatro primeros parámetros. El quinto parámetro toma una lista de invalidación de la configuración. El punto de entrada de inicio del shell se llama desde el punto de entrada principal de una aplicación.  
  
 El punto de entrada de inicio del shell tiene la siguiente firma.  
  
```  
typedef int (__cdecl *STARTFCN)(LPSTR, LPWSTR, int, GUID *, WCHAR *pszSettings);  
```  
  
 Si no desea reemplazar cualquier configuración de la aplicación, deje el valor de la configuración reemplaza el parámetro como un puntero nulo.  
  
 Para reemplazar una o más configuraciones, pase una cadena Unicode que contiene la configuración que se invalide. La cadena es una lista separada por punto y coma de pares nombre / valor. Cada par contiene el nombre de la opción para invalidar, seguido por un signo igual (=), seguido del valor que se aplicará a la configuración.  
  
> [!NOTE]
>  No incluya espacios en blanco en las cadenas Unicode.  
  
 Para valores booleanos, las cadenas siguientes representan el valor true; todas las demás cadenas representan el valor false. Estas cadenas distinguen mayúsculas de minúsculas.  
  
-   \+  
  
-   1  
  
-   -1  
  
-   en  
  
-   true  
  
-   sí  
  
## <a name="example"></a>Ejemplo  
 Para deshabilitar complementos y cambiar la ubicación de proyectos predeterminada para la aplicación, puede establecer el último parámetro a "AddinsAllowed=false;DefaultProjectsLocation=%USERPROFILE%\temp".  
  
## <a name="see-also"></a>Vea también  
 [Personalización del Shell aislado](../extensibility/customizing-the-isolated-shell.md)   
 [Archivos .Pkgdef](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)
