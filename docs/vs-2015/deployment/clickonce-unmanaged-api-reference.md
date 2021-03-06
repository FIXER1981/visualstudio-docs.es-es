---
title: Referencia de la API no administrada de ClickOnce | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- LaunchApplication [ClickOnce unmanaged]
- ClickOnce, unmanaged APIs
- CleanOnlineAppCache [ClickOnce unmanaged]
- CleanOnlineAppCacheW interface [ClickOnce unmanaged]
- GetDeploymentDataFromManifest [ClickOnce unmanaged]
ms.assetid: ec002138-4054-456d-bcc1-79ac2f4a4fd7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 714d7b18995bf1ad51b07e02227e440879f73c9e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68192304"
---
# <a name="clickonce-unmanaged-api-reference"></a>Referencia de la API no administrada de ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] API públicas no administradas de dfshim.dll.  
  
## <a name="cleanonlineappcache"></a>CleanOnlineAppCache  
 Limpia o desinstala todas las aplicaciones en línea de la [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] memoria caché de la aplicación.  
  
### <a name="return-value"></a>Valor devuelto  
 Si se realiza correctamente, Devuelve S_OK; de lo contrario, devuelve un valor HRESULT que representa el error. Si se produce una excepción administrada, devuelve 0x80020009 (DISP_E_EXCEPTION).  
  
### <a name="remarks"></a>Comentarios  
 Si se llama a CleanOnlineAppCache, se iniciará el [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] servicio si aún no se está ejecutando.  
  
## <a name="getdeploymentdatafrommanifest"></a>GetDeploymentDataFromManifest  
 Recupera información de implementación del manifiesto y la dirección URL de activación.  
  
### <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|Tipo|  
|---------------|-----------------|----------|  
|`pcwzActivationUrl`|Puntero a `ActivationURL`.|LPCWSTR|  
|`pcwzPathToDeploymentManifest`|Puntero a `PathToDeploymentManifest`.|LPCWSTR|  
|`pwzApplicationIdentity`|Un puntero a un búfer para recibir una cadena terminada en NULL que especifica la identidad de aplicación completa devuelta.|LPWSTR|  
|`pdwIdentityBufferLength`|Un puntero a un valor DWORD que es la longitud del `pwzApplicationIdentity` búfer, en WCHARs. Esto incluye el espacio para el carácter de terminación NULL.|LPDWORD|  
|`pwzProcessorArchitecture`|Un puntero a un búfer para recibir una cadena terminada en NULL que especifica la arquitectura de procesador de la implementación de la aplicación, del manifiesto.|LPWSTR|  
|`pdwArchitectureBufferLength`|Un puntero a un valor DWORD que es la longitud del `pwzProcessorArchitecture` búfer, en WCHARs.|LPDWORD|  
|`pwzApplicationManifestCodebase`|Un puntero a un búfer para recibir una cadena terminada en NULL que especifica el código base del manifiesto de aplicación, del manifiesto.|LPWSTR|  
|`pdwCodebaseBufferLength`|Un puntero a un valor DWORD que es la longitud del `pwzApplicationManifestCodebase` búfer, en WCHARs.|LPDWORD|  
|`pwzDeploymentProvider`|Un puntero a un búfer para recibir una cadena terminada en NULL que especifica el proveedor de implementación del manifiesto, si está presente. De lo contrario, se devuelve una cadena vacía.|LPWSTR|  
|`pdwProviderBufferLength`|Un puntero a un valor DWORD que es la longitud de `pwzProviderBufferLength` .|LPDWORD|  
  
### <a name="return-value"></a>Valor devuelto  
 Si se realiza correctamente, Devuelve S_OK; de lo contrario, devuelve un valor HRESULT que representa el error. Devuelve HRESULTFROMWIN32 (ERROR_INSUFFICIENT_BUFFER) si un búfer es demasiado pequeño.  
  
### <a name="remarks"></a>Comentarios  
 Los punteros no deben ser null. `pcwzActivationUrl` y `pcwzPathToDeploymentManifest` no deben estar vacíos.  
  
 Es responsabilidad del autor de la llamada limpiar la dirección URL de activación. Por ejemplo, si se agregan caracteres de escape en los que se necesitan o se quita la cadena de consulta.  
  
 Es responsabilidad del llamador limitar la longitud de entrada. Por ejemplo, la longitud máxima de la dirección URL es 2 KB.  
  
## <a name="launchapplication"></a>LaunchApplication  
 Inicia o instala una aplicación mediante una dirección URL de implementación.  
  
### <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|Tipo|  
|---------------|-----------------|----------|  
|`deploymentUrl`|Un puntero a una cadena terminada en NULL que contiene la dirección URL del manifiesto de implementación.|LPCWSTR|  
|`data`|Reservado para un uso futuro. Debe ser NULL.|LPVOID|  
|`flags`|Reservado para un uso futuro. Debe ser 0.|DWORD|  
  
### <a name="return-value"></a>Valor devuelto  
 Si se realiza correctamente, Devuelve S_OK; de lo contrario, devuelve un valor HRESULT que representa el error. Si se produce una excepción administrada, devuelve 0x80020009 (DISP_E_EXCEPTION).  
  
## <a name="see-also"></a>Consulte también  
 <xref:System.Deployment.Application.DeploymentServiceCom.CleanOnlineAppCache%2A>
