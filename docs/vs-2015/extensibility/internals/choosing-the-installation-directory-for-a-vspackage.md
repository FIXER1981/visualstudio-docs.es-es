---
title: Elección del directorio de instalación de un VSPackage | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, installation directory
ms.assetid: 01fbbb5b-f747-446c-afe0-2a081626a945
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c4100c045181f32e51abcc59116a69cad6cc33b5
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "65697245"
---
# <a name="choosing-the-installation-directory-for-a-vspackage"></a>Selección del directorio de instalación de un VSPackage
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Un VSPackage y sus archivos auxiliares deben estar en el sistema de archivos de un usuario. La ubicación depende de si el VSPackage está o no administrado, el esquema de control de versiones en paralelo y la elección del usuario.  
  
## <a name="unmanaged-vspackages"></a>VSPackages no administrados  
 Un VSPackage no administrado es un servidor COM que se puede instalar en cualquier ubicación. La información de registro debe reflejar con precisión su ubicación. La interfaz de usuario (IU) del instalador debe proporcionar una ubicación predeterminada como subdirectorio de la propiedad ProgramFilesFolder Windows Installer. Por ejemplo:  
  
 ProgramFilesFolder MyCompany\MyVSPackageProduct\V1.0\  
  
 Se debe permitir al usuario cambiar el directorio predeterminado para dar cabida a los usuarios que mantienen una pequeña partición de arranque y prefieren instalar aplicaciones y herramientas en otro volumen.  
  
 Si el esquema en paralelo usa un VSPackage con versiones, puede usar subdirectorios para almacenar distintas versiones. Por ejemplo:  
  
 ProgramFilesFolder MyCompany\MyVSPackageProduct\V1.0\2002\  
  
 ProgramFilesFolder MyCompany\MyVSPackageProduct\V1.0\2003\  
  
 ProgramFilesFolder MyCompany\MyVSPackageProduct\V1.0\2005\  
  
## <a name="managed-vspackages"></a>VSPackages administrado  
 Los VSPackages administrados también se pueden instalar en cualquier ubicación. Sin embargo, considere la posibilidad de instalarlos siempre en la caché de ensamblados global (GAC) para reducir los tiempos de carga de ensamblados. Dado que los VSPackages administrados son siempre ensamblados con nombre seguro, su instalación en la GAC significa que la comprobación de la firma de nombre seguro solo se realiza en el momento de la instalación. Los ensamblados con nombre seguro instalados en otro lugar del sistema de archivos deben comprobarse con sus firmas cada vez que se cargan. Al instalar los VSPackages administrados en la GAC, use el modificador **/Assembly** de la herramienta regpkg para escribir entradas del registro que apunten al nombre seguro del ensamblado.  
  
 Si instala los VSPackages administrados en una ubicación distinta de la GAC, siga los consejos anteriores proporcionados para los VSPackages no administrados para elegir las jerarquías de directorios. Use el modificador **/codebase** de la herramienta regpkg para escribir entradas del registro que apunten a la ruta de acceso del ensamblado del VSPackage.  
  
 Para obtener más información, vea [registrar y anular el registro de VSPackages](../../extensibility/registering-and-unregistering-vspackages.md).  
  
## <a name="satellite-dlls"></a>archivos DLL satélite  
 Por Convención, los archivos dll satélite de VSPackage, que contienen recursos para una configuración regional determinada, se encuentran en subdirectorios del directorio de VSPackage. Los subdirectorios corresponden a los valores de ID. de configuración regional (LCID).  
  
 La [Administración de VSPackages](../../extensibility/managing-vspackages.md) indica que las entradas del registro controlan dónde [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] busca realmente un archivo dll satélite de VSPackage. Sin embargo, [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] intenta cargar un archivo dll satélite en un subdirectorio denominado para un valor LCID, en el orden siguiente:  
  
1. LCID predeterminado (VS LCID por ejemplo \ 1033 para inglés)  
  
2. LCID predeterminado con el subidioma predeterminado.  
  
3. LCID predeterminado del sistema.  
  
4. LCID predeterminado del sistema con el subidioma predeterminado.  
  
5. Inglés de EE. UU. (. \ 1033 o .\0x409).  
  
   Si el archivo DLL de VSPackage incluye recursos y la entrada del registro SatelliteDll\DllName apunta a él, [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] intenta cargarlos en el orden anterior.  
  
## <a name="see-also"></a>Consulte también  
 [Elegir entre VSPackages compartidos y con control de versiones](../../extensibility/choosing-between-shared-and-versioned-vspackages.md)   
 [Administrar VSPackages](../../extensibility/managing-vspackages.md)   
 [Registro de paquetes administrados](https://msdn.microsoft.com/f69e0ea3-6a92-4639-8ca9-4c9c210e58a1)
