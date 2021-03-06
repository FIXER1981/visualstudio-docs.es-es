---
title: '&lt;entryPoint &gt; (elemento, aplicación ClickOnce) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#commandLine
- urn:schemas-microsoft-com:asm.v2#entryPoint
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <entryPoint> element [ClickOnce application manifest]
- manifests [ClickOnce], entryPoint element
ms.assetid: 10ad3083-10c1-4189-a870-9bba2eab244f
caps.latest.revision: 35
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 9ce9fcbddf54dff0ee8574d0c2a5a3df4d8b5c7e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68193504"
---
# <a name="ltentrypointgt-element-clickonce-application"></a>&lt;entryPoint &gt; (elemento, aplicación ClickOnce)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Identifica el ensamblado que se debe ejecutar cuando esta [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplicación se ejecuta en un equipo cliente.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
      <entryPoint  
   name  
>  
   <assemblyIdentity  
      name  
      version  
      processorArchitecture  
      language  
   />  
   <commandLine  
      file  
      parameters  
   />  
   <customHostRequired />  
   <customUX />  
</entryPoint>  
```  
  
## <a name="elements-and-attributes"></a>Atributos y elementos  
 El elemento `entryPoint` es obligatorio y se encuentra en el espacio de nombres `urn:schemas-microsoft-com:asm.v2` . Solo puede haber un `entryPoint` elemento definido en un manifiesto de aplicación.  
  
 El elemento `entryPoint` tiene el siguiente atributo.  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`name`|Opcional. .NET Framework no usa este valor.|  
  
 `entryPoint` tiene los siguientes elementos.  
  
## <a name="assemblyidentity"></a>assemblyIdentity  
 Necesario. El rol de `assemblyIdentity` y sus atributos se define en el [ \<assemblyIdentity> elemento](../deployment/assemblyidentity-element-clickonce-application.md).  
  
 El `processorArchitecture` atributo de este elemento y el `processorArchitecture` atributo definido en el `assemblyIdentity` resto del manifiesto de aplicación deben coincidir.  
  
## <a name="commandline"></a>commandLine  
 Necesario. Debe ser un elemento secundario del `entryPoint` elemento. No tiene elementos secundarios y tiene los atributos siguientes.  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`file`|Necesario. Referencia local al ensamblado de inicio de la [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplicación. Este valor no puede contener separadores de ruta de barra diagonal (/) ni de barra diagonal inversa ( \\ ).|  
|`parameters`|Necesario. Describe la acción que se debe llevar a cabo con el punto de entrada. El único valor válido es `run` ; si se proporciona una cadena en blanco, `run` se supone.|  
  
## <a name="customhostrequired"></a>customHostRequired  
 Opcional. Si se incluye, especifica que esta implementación contiene un componente que se implementará dentro de un host personalizado y no es una aplicación independiente.  
  
 Si este elemento está presente, los `assemblyIdentity` `commandLine` elementos y no deben estar presentes también. En caso de que se produzcan, generará [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] un error de validación durante la instalación.  
  
 Este elemento no tiene atributos ni elementos secundarios.  
  
## <a name="customux"></a>customUX  
 Opcional. Especifica que un instalador personalizado instala y mantiene la aplicación, y no crea una entrada en el menú Inicio, acceso directo, ni la entrada agregar o quitar programas.  
  
```  
<customUX xmlns="urn:schemas-microsoft-com:clickonce.v1" />  
```  
  
 Una aplicación que incluye el elemento customUX debe proporcionar un instalador personalizado que utilice la <xref:System.Deployment.Application.InPlaceHostingManager> clase para realizar las operaciones de instalación. Una aplicación con este elemento no se puede instalar haciendo doble clic en su manifiesto o setup.exe programa previo de requisito previo. El instalador personalizado puede crear entradas del menú Inicio, accesos directos y entradas agregar o quitar programas. Si el instalador personalizado no crea una entrada agregar o quitar programas, debe almacenar el identificador de suscripción proporcionado por la <xref:System.Deployment.Application.GetManifestCompletedEventArgs.SubscriptionIdentity%2A> propiedad y permitir que el usuario desinstale la aplicación más adelante mediante una llamada al <xref:System.Deployment.Application.InPlaceHostingManager.UninstallCustomUXApplication%2A> método. Para obtener más información, vea [Tutorial: crear un instalador personalizado para una aplicación ClickOnce](../deployment/walkthrough-creating-a-custom-installer-for-a-clickonce-application.md).  
  
## <a name="remarks"></a>Comentarios  
 Este elemento identifica el ensamblado y el punto de entrada de la [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplicación.  
  
 No se puede usar `commandLine` para pasar parámetros a la aplicación en tiempo de ejecución. Puede tener acceso a los parámetros de cadena de consulta para una [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] implementación desde la de la aplicación <xref:System.AppDomain> . Para obtener más información, vea [Cómo: recuperar información de la cadena de consulta en una aplicación ClickOnce en línea](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra un `entryPoint` elemento en un manifiesto de aplicación para una [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplicación. Este ejemplo de código forma parte de un ejemplo mayor proporcionado para el tema de [manifiesto de aplicación ClickOnce](../deployment/clickonce-application-manifest.md) .  
  
```  
<!-- Identify the main code entrypoint. -->  
<!-- This code runs the main method in an executable assembly. -->  
  <entryPoint>  
    <assemblyIdentity   
      name="MyApplication"   
      version="1.0.0.0"  
      language="neutral"  
      processorArchitecture="x86" />  
    <commandLine file="MyApplication.exe" parameters="" />  
  </entryPoint>  
```  
  
## <a name="see-also"></a>Consulte también  
 [Manifiesto de aplicación ClickOnce](../deployment/clickonce-application-manifest.md)
