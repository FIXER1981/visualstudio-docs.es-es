---
title: '&lt;Description &gt; (elemento, implementación de ClickOnce) | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#description
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <description> element [ClickOnce deployment manifest]
ms.assetid: 18f6919e-a3ab-4942-a57d-167fabfac44e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6c359b188894c40f017e3d2a0e06d52de87e9c5f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "62928800"
---
# <a name="ltdescriptiongt-element-clickonce-deployment"></a>&lt;Description &gt; (elemento, implementación de ClickOnce)
Identifica la información de la aplicación que se usa para crear una presencia de Shell y un elemento **Agregar o quitar programas** en el panel de control.

## <a name="syntax"></a>Sintaxis

```xml

      <description 
   publisher 
   product
   suiteName
   supportUrl
/>
```

## <a name="elements-and-attributes"></a>Elementos y atributos
 El elemento `description` es obligatorio y se encuentra en el espacio de nombres `urn:schemas-microsoft-com:asm.v1` . No contiene elementos secundarios y tiene los atributos siguientes.

|Atributo|Descripción|
|---------------|-----------------|
|`publisher`|Necesario. Identifica el nombre de la compañía que se usa para la ubicación de los iconos en el menú **Inicio** de Windows y en el elemento **Agregar o quitar programas** del panel de control, cuando la implementación está configurada para instalarse.|
|`product`|Necesario. Identifica el nombre completo del producto. Se usa como título del icono instalado en el menú **Inicio** de Windows.|
|`suiteName`|Opcional. Identifica una subcarpeta de la `publisher` carpeta en el menú **Inicio** de Windows.|
|`supportUrl`|Opcional. Especifica una dirección URL de soporte que se muestra en el elemento **Agregar o quitar programas** del panel de control. También se crea un acceso directo a esta dirección URL para la compatibilidad con aplicaciones en el menú **Inicio** de Windows, cuando la implementación está configurada para la instalación.|

## <a name="remarks"></a>Comentarios
 El elemento Description es obligatorio en todas las configuraciones de implementación.

## <a name="example"></a>Ejemplo
 En el ejemplo de código siguiente se muestra un `description` elemento en un [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifiesto de implementación. Este ejemplo de código forma parte de un ejemplo mayor proporcionado para el tema [manifiesto de implementación de ClickOnce](../deployment/clickonce-deployment-manifest.md) .

```xml
<description
  asmv2:publisher="My Company Name"
  asmv2:product="My Application"
  xmlns="urn:schemas-microsoft-com:asm.v1" />
```

## <a name="see-also"></a>Consulte también
- [Manifiesto de implementación de ClickOnce](../deployment/clickonce-deployment-manifest.md)