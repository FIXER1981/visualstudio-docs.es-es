---
title: '&lt;fileAssociation&gt; elemento (aplicación ClickOnce) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <fileAssociation> element [ClickOnce application manifest]
- manifests [ClickOnce], fileAssociation element
ms.assetid: 8f951b4f-54f9-412e-a9e5-af4e379fcf08
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4b31ac34627b244cb61b6fdb5c6ca214675ec045
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "68150843"
---
# <a name="ltfileassociationgt-element-clickonce-application"></a>&lt;fileAssociation&gt; elemento (aplicación ClickOnce)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Identifica una extensión de archivo que se asociará con la aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
<fileAssociation  
    xmlns="urn:schemas-microsoft-com:clickonce.v1"  
    extension  
    description  
    progid  
    defaultIcon  
/>  
```  
  
## <a name="elements-and-attributes"></a>Elementos y atributos  
 El elemento `fileAssociation` es opcional. El elemento tiene los atributos siguientes.  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`extension`|Necesario. La extensión de archivo que se asociará con la aplicación.|  
|`description`|Necesario. Una descripción del tipo de archivo para su uso por el shell.|  
|`progid`|Necesario. Un nombre que identifica el tipo de archivo.|  
|`defaultIcon`|Necesario. Especifica el icono que se utiliza para los archivos con esta extensión. El archivo de icono debe especificarse utilizando la [ \<archivo > elemento](../deployment/file-element-clickonce-application.md) dentro de la [ \<ensamblado > elemento](../deployment/assembly-element-clickonce-application.md) que contiene este elemento.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento debe incluir una referencia de espacio de nombres XML para "urn: schemas-microsoft-v1". Si el `<fileAssociation>` se usa el elemento, debe ir detrás del `<application>` elemento en su elemento primario [ \<ensamblado > elemento](../deployment/assembly-element-clickonce-application.md).  
  
 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] no se sobrescribirá las asociaciones de archivo existentes. Sin embargo, una aplicación ClickOnce puede reemplazar la extensión de archivo para el usuario actual. Después de desinstala la aplicación ClickOnce, ClickOnce elimina la asociación de archivo para el usuario y la asociación de cada equipo nuevo está activa.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código ilustra `fileAssociation` elementos en una aplicación de manifiesto para una aplicación de editor de texto implementada mediante [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]. Este ejemplo de código también incluye el [ \<archivo > elemento](../deployment/file-element-clickonce-application.md) requerido por la `defaultIcon` atributo.  
  
```  
<file name="text.ico" size="4286">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>0joAqhmfeBb93ZneZv/oTMP2brY=</dsig:DigestValue>  
  </hash>  
</file>  
<file name="writing.ico" size="9662">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>2cL2U7cm13nG40v9MQdxYKazIwI=</dsig:DigestValue>  
  </hash>  
</file>  
<fileAssociation xmlns="urn:schemas-microsoft-com:clickonce.v1" extension=".text" description="Text  Document (ClickOnce)" progid="Text.Document" defaultIcon="text.ico" />  
<fileAssociation xmlns="urn:schemas-microsoft-com:clickonce.v1" extension=".writing" description="Writings (ClickOnce)" progid="Writing.Document" defaultIcon="writing.ico" />  
```  
  
## <a name="see-also"></a>Vea también  
 [ClickOnce Application Manifest](../deployment/clickonce-application-manifest.md)
