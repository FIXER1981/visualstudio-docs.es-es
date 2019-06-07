---
title: '&lt;compatibleFrameworks&gt; elemento (implementación ClickOnce) | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <compatibleFrameworks> element [ClickOnce deployment manifest]
ms.assetid: f6c3ee55-9e65-403d-8664-3ebde872c7d4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 99db3d51414197df469aaa2eabe97e0967c31b05
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2019
ms.locfileid: "66746040"
---
# <a name="ltcompatibleframeworksgt-element-clickonce-deployment"></a>&lt;compatibleFrameworks&gt; elemento (implementación ClickOnce)
Identifica las versiones de .NET Framework en las que se puede instalar y ejecutar esta aplicación.

> [!NOTE]
> [*MageUI.exe* ](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client) no admite el `compatibleFrameworks` elemento cuando se guarda un manifiesto de aplicación que ya se ha firmado con un certificado mediante [ *MageUI.exe*](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client). En su lugar, debe usar [*Mage.exe*](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool).

## <a name="syntax"></a>Sintaxis

```xml
<compatibleFrameworks
      SupportUrl> 
   <framework
      targetVersion
      profile
      supportedRuntime
   /> 
</ compatibleFrameworks>
```

## <a name="elements-and-attributes"></a>Elementos y atributos
 El `compatibleFrameworks` elemento es necesario para los manifiestos de implementación que tienen como destino el [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] en tiempo de ejecución proporcionado por .NET Framework 4 o posterior. El `compatibleFrameworks` elemento contiene uno o varios `framework` elementos que especifican las versiones de .NET Framework en el que se puede ejecutar esta aplicación. El [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] en tiempo de ejecución ejecutará la aplicación en la primera disponible `framework` en esta lista.

 En la tabla siguiente se enumera el atributo que el `compatibleFrameworks` admite el elemento.

|Atributo|Descripción|
|---------------|-----------------|
|`S` `upportUrl`|Opcional. Especifica una dirección URL donde se puede descargar la versión de .NET Framework compatible preferida.|

## <a name="framework"></a>marco de trabajo
 Obligatorio. En la tabla siguiente se enumera los atributos que el `framework` admite el elemento.

|Atributo|Descripción|
|---------------|-----------------|
|`targetVersion`|Obligatorio. Especifica el número de versión de .NET Framework de destino.|
|`profile`|Obligatorio. Especifica el perfil de .NET Framework de destino.|
|`supportedRuntime`|Obligatorio. Especifica el número de versión del tiempo de ejecución asociada con el destino es .NET Framework.|

## <a name="remarks"></a>Comentarios

## <a name="example"></a>Ejemplo
 El siguiente ejemplo de código muestra un `compatibleFrameworks` elemento en un [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifiesto de implementación. Esta implementación se puede ejecutar en el [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)]. También puede ejecutar en .NET Framework 4 porque es un superconjunto de la [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)].

```xml
<compatibleFrameworks xmlns="urn:schemas-microsoft-com:clickonce.v2">
  <framework
      targetVersion="4.0"
      profile="Client"
      supportedRuntime="4.0.30319" />
</compatibleFrameworks>
```

## <a name="see-also"></a>Vea también
- [Manifiesto de implementación de ClickOnce](../deployment/clickonce-deployment-manifest.md)