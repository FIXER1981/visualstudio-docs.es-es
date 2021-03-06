---
title: Registrando servicios | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
helpviewer_keywords:
- services, registering
ms.assetid: c4ebac40-0374-4dda-948e-06fdda0e9c81
caps.latest.revision: 8
manager: jillfra
ms.openlocfilehash: 64f2afa6e853978e919e466f91475bed1e8d698c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "62971295"
---
# <a name="registering-services"></a>Registrar servicios
Para admitir la carga a petición, un proveedor de servicios debe registrar sus servicios globales con [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
 Durante el desarrollo, los proveedores de servicios administrados registran servicios e invalidaciones de servicio agregando atributos al código fuente de los paquetes y, después, compilando los paquetes el IDE de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] . Esta opción ejecuta la utilidad RegPkg.exe en el ensamblado resultante, registra el paquete y lo prepara para la implementación. Para obtener más información, consulte [Cómo: registrar un servicio](../misc/how-to-register-a-service.md).  
  
 Los proveedores de servicios no administrados deben registrar los servicios que se ofrecen con [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] en la sección de servicios o en la de invalidaciones de servicios del registro del sistema. En el siguiente fragmento de un archivo .reg se muestra cómo se puede registrar el servicio, SVsTextManager:  
  
```  
[HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\<version number>\Services\{F5E7E71D-1401-11d1-883B-0000F87579D2}]  
@="{F5E7E720-1401-11d1-883B-0000F87579D2}"  
"Name"="SVsTextManager"  
```  
  
 En el ejemplo anterior, version number es la versión de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], por ejemplo, 7.1 u 8.0, la clave {F5E7E71D-1401-11d1-883B-0000F87579D2} es el identificador de servicio (SID) del servicio, SVsTextManager, y el valor predeterminado {F5E7E720-1401-11d1-883B-0000F87579D2} es el GUID de paquete del administrador de texto VSPackage, que ofrece el servicio.  
  
## <a name="remote-services-and-background-threads"></a>Servicios remotos y subprocesos en segundo plano  
 Los servicios que ofrezca no están disponibles automáticamente de forma remota ni para los subprocesos en segundo plano. Para que estén disponibles, debe compilar y registrar una biblioteca de tipos.  
  
 Con código no administrado que utilice la biblioteca de Visual Studio (VSL), puede registrar la biblioteca de tipos de esta manera:  
  
```  
#define VSL_REGISTER_TYPE_LIB TRUE  
#include <VSLPackageDllEntryPoints.cpp>  
```  
  
 Con código administrado, puede agregar un paso posterior a la compilación similar al siguiente:  
  
```  
regasm /tlb MyAssembly.dll  
```  
  
## <a name="see-also"></a>Consulte también  
 [Uso y suministro de servicios](../extensibility/using-and-providing-services.md)   
 [Conceptos básicos del servicio](../extensibility/internals/service-essentials.md)