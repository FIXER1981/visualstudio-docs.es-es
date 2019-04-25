---
title: Solucionar problemas de seguridad de la solución de Office
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- security [Office development in Visual Studio], troubleshooting
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 921bef3514b802672296dda6d680b665f1f42482
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56632503"
---
# <a name="troubleshoot-office-solution-security"></a>Solucionar problemas de seguridad de la solución de Office
  En este tema contiene sugerencias para resolver problemas comunes que pueden surgir al trabajar con la protección de las soluciones de Office.

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

## <a name="trusted-solutions-cannot-be-installed-from-restricted-sites"></a>No se puede instalar las soluciones de confianza desde sitios restringidos
 Los usuarios no pueden instalar una solución desde una ubicación web si el sitio Web se muestra en la zona Sitios restringidos de Internet Explorer. Esto es cierto incluso si la solución está firmada con un certificado de confianza.

 La dirección URL del manifiesto de implementación se puede clasificar en uno de los cinco zonas:

- Mi equipo

- Internet

- Intranet local

- Sitios de confianza

- Sitios restringidos

  Si la ubicación del manifiesto de implementación se ha asignado a la zona Sitios restringidos, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] no instala la solución. Si la ubicación se conoce y puede ser de confianza, el usuario puede quitar la ubicación de la zona Sitios restringidos e instalar la solución. Para obtener información acerca de cómo administrar zonas, consulte [Configuring ClickOnce Trusted Publishers](http://go.microsoft.com/fwlink/?LinkId=94774).

## <a name="solutions-cannot-be-installed-from-network-file-shares-or-web-locations-when-internet-explorer-enhanced-security-configuration-or-internet-explorer-7-is-installed"></a>Las soluciones no se puede instalar desde ubicaciones web o de recursos compartidos de archivos de red cuando se instala la configuración de seguridad mejorada de Internet Explorer o Internet Explorer 7
 Internet Explorer Enhanced Security Configuration (IEESC) en Windows Server 2003 y versiones posteriores e Internet Explorer 7 y versiones posterior, restringe la capacidad de los usuarios a navegar por Internet. Cuando los usuarios intentan instalar compartan soluciones de Office desde un archivo de red o ubicación web, podría obtener el mensaje de error siguiente: "La funcionalidad personalizada de esta aplicación no funcionará porque el certificado utilizado para firmar el manifiesto de implementación para *SolutionName* no es de confianza. Póngase en contacto con su administrador para obtener más ayuda."

 Con IEESC e Internet Explorer 7 y versiones posterior, si la dirección URL del manifiesto de implementación se clasifica por categorías en la zona de Internet, el manifiesto debe tener un certificado desde un editor de confianza o no se puede instalar la solución. Sin IEESC, el comportamiento predeterminado es preguntar al usuario final para tomar una decisión de confianza.

 Para administrar el efecto de IEESC e Internet Explorer 7 y versiones posteriores, identificar sitios Web y rutas de nomenclatura universal (UNC) de la convención confía y agregarlos a una de las zonas de seguridad de confianza (intranet Local o sitios de confianza). Para obtener información acerca de cómo administrar zonas, consulte [editores de confianza de ClickOnce configurar](http://go.microsoft.com/fwlink/?LinkId=94774).

## <a name="see-also"></a>Vea también
- [Proteger soluciones de Office](../vsto/securing-office-solutions.md)
