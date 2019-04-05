---
title: Compilador de colores de VSIX | Documentos de Microsoft
ms.date: 11/15/2016
ms.topic: conceptual
ms.assetid: 99395da7-ec34-491d-9baa-0590d23283ce
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c878eb55dbbdeacf0984b399949b2c3bbb7550b8
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "58998475"
---
# <a name="vsix-color-compiler"></a>Compilador de colores de VSIX
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

La herramienta de compilador de Color de extensión de Visual Studio es una aplicación de consola que toma un archivo .xml que representa los colores para temas existentes de Visual Studio y la convierte a un .pkgdef de archivos para que se pueden usar esos colores en Visual Studio. Dado que es fácil de comparar las diferencias entre archivos .xml, esta herramienta es útil para administrar los colores personalizados en el control de código fuente. También puede enlazarse en entornos de compilación para que el resultado de la compilación es un archivo .pkgdef válido.  
  
 **Esquema XML de tema**  
  
 Un archivo .xml de tema completa tiene este aspecto:  
  
```xml  
<Themes>  
      <!—one or Theme elements -->  
      <Theme>  
        <!-- one or more Category elements -->  
        <Category>  
          <!-- one or more Color elements -->  
          <Color>  
            <!-- zero or one Background element -->  
            <Background />  
            <!-- zero or one Foreground element -->  
            <Foreground />  
          </Color>  
        </Category>  
      </Theme>  
</Themes>  
```  
  
 **Tema**  
  
 El \<tema > elemento define un tema completo. Un tema debe contener al menos un \<categoría > elemento. Elementos de tema se definen de forma similar al siguiente:  
  
```xml  
<Theme Name="name" GUID="guid">  
      <!-- one or more Category elements -->  
</Theme>  
```  
  
|||  
|-|-|  
|**Attribute**|**Definición**|  
|Name|[Obligatorio] El nombre del tema|  
|GUID|[Obligatorio] GUID del tema (debe coincidir con el formato de GUID)|  
  
 Al crear colores personalizados para Visual Studio, los colores deben definirse para los temas siguientes. Si ningún colores existen para un tema concreto, Visual Studio intenta cargar los colores que faltan desde el tema claro.  
  
|||  
|-|-|  
|**Nombre del tema**|**Theme GUID**|  
|Claro|{de3dbbcd-f642-433c-8353-8f1df4370aba}|  
|Oscuro|{1ded0138-47ce-435e-84ef-9ec1f439b749}|  
|Azul|{a4d6a176-b948-4b29-8c66-53c97a1ed7d0}|  
|Contraste alto|{a4d6a176-b948-4b29-8c66-53c97a1ed7d0}|  
  
 **Categoría**  
  
 El \<categoría > elemento define una colección de colores en un tema. Los nombres de categoría proporcionan agrupaciones lógicas y deben definirse como restrictiva como sea posible. Una categoría debe contener al menos un \<Color > elemento. Los elementos de categoría se definen de forma similar al siguiente:  
  
```xml  
<Category Name="name" GUID="guid">  
      <!-- one or more Color elements -->  
 </Category>  
```  
  
|||  
|-|-|  
|**Attribute**|**Definición**|  
|Name|[Obligatorio] El nombre de la categoría|  
|GUID|[Obligatorio] GUID de la categoría (debe coincidir con el formato de GUID)|  
  
 **Color**  
  
 El \<Color > elemento define un color de un componente o el estado de la interfaz de usuario. El esquema de nomenclatura preferido para un color es [tipo de interfaz de usuario] [estado]. No use la palabra "color", ya que es redundante. Un color debe indicar claramente el tipo de elemento y las situaciones o "state", para que se aplicará el color. Un color no debe estar vacío y debe contener uno o ambos de un \<en segundo plano > y \<Foreground > elemento. Se definen los elementos de color similar al siguiente:  
  
```xml  
<Color Name="name">  
        <Background /> <!-- zero or one Background element -->  
        <Foreground /> <!-- zero or one Foreground element -->  
 </Color>  
```  
  
|||  
|-|-|  
|**Attribute**|**Definición**|  
|Name|[Obligatorio] El nombre del color|  
  
 **En segundo plano o primer plano**  
  
 El \<en segundo plano > y \<Foreground > elementos definen el valor y tipo para el fondo o el primer plano de un elemento de interfaz de usuario de un color. Estos elementos no tienen elementos secundarios.  
  
```xml  
<Background Type="type" Source="int" />  
<Foreground Type="type" Source="int" />  
```  
  
|||  
|-|-|  
|**Attribute**|**Definición**|  
|Tipo|[Obligatorio] El tipo del color. Puede ser uno de los siguientes:<br /><br /> *CT_INVALID:* El color no es válida o no.<br /><br /> *CT_RAW:* Valor sin formato ARGB.<br /><br /> *CT_COLORINDEX:* NO USE.<br /><br /> *CT_SYSCOLOR:* Un color del sistema de Windows desde SysColor.<br /><br /> *CT_VSCOLOR:* Un color de Visual Studio en __VSSYSCOLOREX.<br /><br /> *CT_AUTOMATIC:* El color automático.<br /><br /> *CT_TRACK_FOREGROUND:* NO USE.<br /><br /> *CT_TRACK_BACKGROUND:* NO USE.|  
|Origen|[Obligatorio] El valor del color representado en formato hexadecimal|  
  
 Todos los valores admitidos por la enumeración __VSCOLORTYPE son compatibles con el esquema en el atributo de tipo. Sin embargo, se recomienda que use solo CT_RAW y CT_SYSCOLOR.  
  
 **Todos juntos**  
  
 Esto es un ejemplo sencillo de un archivo .xml de tema válido:  
  
```xml  
<Themes>  
  <Theme Name="Light" GUID="{de3dbbcd-f642-433c-8353-8f1df4370aba}">  
    <Category Name="MyCategory" GUID="{0A96238B-70CE-4479-9170-EECEAA3FCD58}">  
      <Color Name="MyActiveBorder">  
        <Background Type="CT_RAW" Source="FFCCCEDB" />  
      </Color>  
    </Category>  
  </Theme>  
</Themes>  
```  
  
## <a name="how-to-use-the-tool"></a>Cómo usar la herramienta  
 **Sintaxis**  
  
 VsixColorCompiler \<archivo XML > \<archivo PkgDef > \<Args opcional >  
  
 **Argumentos**  
  
||||  
|-|-|-|  
|**Nombre del conmutador**|**Notas**|**Obligatorio u opcional**|  
|Sin nombre (archivo .xml)|Esto es el primer parámetro sin nombre y es la ruta de acceso al archivo XML para convertir.|Obligatorio|  
|Sin nombre (archivo .pkgdef)|Esto es el segundo parámetro sin nombre y es la ruta de acceso de salida para el archivo .pkgdef generado.<br /><br /> Predeterminado: \<Nombre del archivo XML > .pkgdef|Optional|  
|/noLogo|Al establecer esta marca detiene la información de producto y copyright de impresión.|Optional|  
|/?|Imprimir información de ayuda.|Optional|  
|/help|Imprimir información de ayuda.|Optional|  
  
 **Ejemplos**  
  
-   VsixColorCompiler D:\xml\colors.xml D:\pkgdef\colors.pkgdef  
  
-   VsixColorCompiler D:\xml\colors.xml /noLogo  
  
## <a name="notes"></a>Notas  
  
-   Esta herramienta requiere que se ha instalado la versión más reciente del tiempo de ejecución de VC ++.  
  
-   Solo los archivos solo se admiten. No se admite la conversión de forma masiva a través de rutas de carpeta.  
  
## <a name="sample-output"></a>Resultados de ejemplo  
 El archivo .pkgdef generado por la herramienta será similar a la siguiente claves:  
  
```  
[$RootKey$\Themes\{de3dbbcd-f642-433c-8353-8f1df4370aba}\Environment]  
"Data"=hex:3a,00,00,00,0b,00,00,00,01,00,00,00,c3,d9,4e,62,fd,bd,fa,41,96,c3,7c,82,4e,a3,2e,3d,01,00,00,00,0c,00,00,00,41,63,74,69,76,65,42,6f,72,64,65,72,01,cc,ce,db,ff,01,33,31,24,ff  
  
[$RootKey$\Themes\{de3dbbcd-f642-433c-8353-8f1df4370aba}\TreeView]  
"Data"=hex:38,00,00,00,0b,00,00,00,01,00,00,00,8e,f0,ec,92,13,8b,f4,4c,99,e9,ae,26,92,38,21,85,01,00,00,00,0a,00,00,00,42,61,63,6b,67,72,6f,75,6e,64,01,f5,f5,f5,ff,01,1e,1e,1e,ff  
```
