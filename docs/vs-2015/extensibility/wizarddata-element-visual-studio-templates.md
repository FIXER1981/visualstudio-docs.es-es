---
title: WizardData (elemento) (plantillas de Visual Studio) | Documentos de Microsoft
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#WizardData
helpviewer_keywords:
- WizardData element [Visual Studio Templates]
- <WizardData> element [Visual Studio Templates]
ms.assetid: d0403a16-5d07-4fe5-b474-19ae3d9fd3ab
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d7cd59266a69140ba2ea5a7fd1d1b0b0c72f14c2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "68201929"
---
# <a name="wizarddata-element-visual-studio-templates"></a>WizardData (Elemento, Plantillas de Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Especifica código XML personalizado  
  
 \<VSTemplate>  
 \<WizardData>  
  
## <a name="syntax"></a>Sintaxis  
  
```  
<WizardData>  
    <!-- XML to pass to the custom wizard extension -->  
    ...  
</WizardData>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[VSTemplate](../extensibility/vstemplate-element-visual-studio-templates.md)|Elemento necesario.<br /><br /> Contiene todos los metadatos de la plantilla de proyecto, la plantilla de elemento o el starter kit de.|  
  
## <a name="text-value"></a>Valor de texto  
 El valor de texto es opcional.  
  
 Este texto especifica el código XML personalizado para pasar a la extensión de asistente personalizada especificada en el [WizardExtension](../extensibility/wizardextension-element-visual-studio-templates.md) elemento.  
  
## <a name="remarks"></a>Comentarios  
 En este elemento se puede especificar cualquier XML. El código XML se pasará como un parámetro a la extensión de asistente personalizada, lo que permite la extensión usar el contenido de este elemento. Se realiza ninguna validación en estos datos.  
  
 El contenido de la `WizardData` elemento se pasa sin cambios, como un parámetro en el diccionario de cadenas de parámetros en el `IWizard.RunStarted` método. El parámetro se denomina $WizardData$.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra los metadatos de la plantilla de proyecto estándar para un [!INCLUDE[csprcs](../includes/csprcs-md.md)] aplicación de Windows.  
  
```  
<VSTemplate Version="3.0.0" Type="Item"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyTemplate</Name>  
        <Description>Template using IWizard extension</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
    <WizardExtension>  
        <Assembly>MyWizard, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a, Custom=null</Assembly>  
        <FullClassName>MyWizard.CustomWizard</FullClassName>  
    </WizardExtension>  
    <WizardData>  
        <!-- XML to pass to the custom wizard extension -->  
    </WizardData>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Vea también  
 [Referencia de esquema de plantillas de Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Crear plantillas para proyectos y elementos en Visual Studio](../ide/creating-project-and-item-templates.md)   
 [WizardExtension (elemento) (plantillas de Visual Studio)](../extensibility/wizardextension-element-visual-studio-templates.md)   
 [Cómo: Usar asistentes con plantillas de proyectos](../extensibility/how-to-use-wizards-with-project-templates.md)
