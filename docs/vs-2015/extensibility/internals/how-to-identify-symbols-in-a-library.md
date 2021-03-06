---
title: 'Cómo: identificar símbolos en una biblioteca | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Call Browser tool, identifying symbols in the library
- Call Browser tool
ms.assetid: 8fb0de61-71e7-42d1-8b41-2ad915474384
caps.latest.revision: 22
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f154c63940189f1a6035246fb7f72ec27be677f5
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68191874"
---
# <a name="how-to-identify-symbols-in-a-library"></a>Identificación de símbolos en una biblioteca
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Las herramientas de exploración de símbolos muestran vistas jerárquicas de símbolos. Los símbolos representan espacios de nombres, objetos, clases, miembros de clase y otros elementos del lenguaje.  
  
 Cada símbolo de la jerarquía se puede identificar mediante la información de navegación pasada por la biblioteca de símbolos al [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Administrador de objetos a través de las interfaces siguientes:  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfoNode>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumNavInfoNodes>.  
  
 La ubicación del símbolo en la jerarquía distingue un símbolo. Permite que las herramientas de exploración de símbolos naveguen a un símbolo específico. La ruta de acceso completa única al símbolo determina la ubicación. Cada elemento de la ruta de acceso es un nodo. La ruta de acceso comienza con el nodo de nivel superior y termina con el símbolo específico. Por ejemplo, si el método M1 es miembro de la clase C1 y C1 está en el espacio de nombres N1, la ruta de acceso completa del método M1 es N1. C1. Conector. Esta ruta de acceso contiene tres nodos: N1, C1 y M1.  
  
 La información de navegación permite al [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Administrador de objetos buscar, seleccionar y mantener seleccionados los símbolos en la jerarquía. Permite navegar de una herramienta de exploración a otra. Al usar **Examinador de objetos** para examinar los símbolos de un [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] proyecto, puede hacer clic con el botón secundario en un método e iniciar la herramienta de **Explorador de llamadas** para mostrar el método en un gráfico de llamadas.  
  
 Dos formas describen la ubicación de los símbolos. El formato canónico se basa en la ruta de acceso completa del símbolo. Representa una posición única del símbolo en la jerarquía. Es independiente de la herramienta de exploración de símbolos. Para obtener la información de forma canónica, el [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Administrador de objetos llama al <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumCanonicalNodes%2A> método. En el formulario de presentación se describe la ubicación del símbolo dentro de una herramienta de exploración de símbolos específica. La posición del símbolo es relativa a la posición de otros símbolos en el hierarchicy. Un símbolo determinado puede tener varias rutas de presentación, pero solo una ruta de acceso canónica. Por ejemplo, si la clase C1 se hereda de la clase C2 y ambas clases están en el espacio de nombres N1, el **Examinador de objetos** muestra el siguiente árbol jerárquico:  
  
```  
N1  
    C1  
        Bases and Interfaces  
            C2  
    C2  
        Bases and Interfaces  
. . . . . . . . . . .  
  
```  
  
 La ruta de acceso canónica de la clase C2, en este ejemplo, es N1 + C2. La ruta de acceso de la presentación de C2 incluye los nodos C1 y "bases e interfaces": N1 + C1 + "bases e interfaces" + C2.  
  
 Para obtener información sobre el formulario de presentación, el administrador de objetos llama al <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumPresentationNodes%2A> método.  
  
## <a name="identifying-a-symbol-in-the-hierarchy"></a>Identificar un símbolo en la jerarquía  
  
#### <a name="to-obtain-canonical-and-presentation-forms-information"></a>Para obtener información de formularios canónicos y de presentación  
  
1. Implemente el método <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumCanonicalNodes%2A>.  
  
     El administrador de objetos llama a este método para obtener la lista de nodos contenidos en la ruta de acceso canónica del símbolo.  
  
    ```vb  
    Public Function EnumCanonicalNodes(ByRef ppEnum As Microsoft.VisualStudio.Shell.Interop.IVsEnumNavInfoNodes) As Integer  
        Dim EnumNavInfoNodes As CallBrowserEnumNavInfoNodes = _New CallBrowserEnumNavInfoNodes(m_strMethod)  
        ppEnum = CType(EnumNavInfoNodes, IVsEnumNavInfoNodes)  
        Return 0  
    End Function  
    ```  
  
    ```csharp  
    public int EnumCanonicalNodes(out Microsoft.VisualStudio.Shell.Interop.IVsEnumNavInfoNodes ppEnum)  
    {  
        CallBrowserEnumNavInfoNodes EnumNavInfoNodes =  
            new CallBrowserEnumNavInfoNodes(m_strMethod);  
        ppEnum = (IVsEnumNavInfoNodes)(EnumNavInfoNodes);  
        return 0;  
    }  
  
    ```  
  
2. Implemente el método <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumPresentationNodes%2A>.  
  
     El administrador de objetos llama a este método para obtener la lista de nodos contenidos en la ruta de acceso de presentación del símbolo.  
  
## <a name="see-also"></a>Consulte también  
 [Compatibilidad con herramientas de exploración de símbolos](../../extensibility/internals/supporting-symbol-browsing-tools.md)   
 [Cómo: registrar una biblioteca con el administrador de objetos](../../extensibility/internals/how-to-register-a-library-with-the-object-manager.md)   
 [Exposición de listas de símbolos proporcionadas por la biblioteca al Administrador de objetos](../../extensibility/internals/how-to-expose-lists-of-symbols-provided-by-the-library-to-the-object-manager.md)
