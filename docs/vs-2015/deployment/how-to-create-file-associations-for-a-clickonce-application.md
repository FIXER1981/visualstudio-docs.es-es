---
title: 'Cómo: crear asociaciones de archivo para una aplicación ClickOnce | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- file associations, ClickOnce applications
- ClickOnce deployment, file associations
ms.assetid: 835230c8-3177-440f-85e3-e40f1d8b4f9d
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 82ffecdc719dad2f38208de00dc95438b3ff36ef
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "65697699"
---
# <a name="how-to-create-file-associations-for-a-clickonce-application"></a>Cómo: Crear asociaciones de archivo para una aplicación ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] las aplicaciones pueden estar asociadas a una o varias extensiones de nombre de archivo, de modo que la aplicación se iniciará automáticamente cuando el usuario abra un archivo de esos tipos. Agregar compatibilidad con la extensión de nombre de archivo a una [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplicación es sencillo.  
  
### <a name="to-create-file-associations-for-a-clickonce-application"></a>Para crear asociaciones de archivo para una aplicación ClickOnce  
  
1. Cree una [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplicación normalmente o use la aplicación existente [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] .  
  
2. Abra el manifiesto de aplicación con un editor de texto o XML, como el Bloc de notas.  
  
3. Busque el elemento `assembly` . Para más información, consulte [Manifiesto de aplicación ClickOnce](../deployment/clickonce-application-manifest.md).  
  
4. Como elemento secundario del `assembly` elemento, agregue un `fileAssociation` elemento. El `fileAssociation` elemento tiene cuatro atributos:  
  
   - `extension`: La extensión de nombre de archivo que desea asociar a la aplicación.  
  
   - `description`: Descripción del tipo de archivo, que aparecerá en el shell de Windows.  
  
   - `progid`: Una cadena que identifica de forma única el tipo de archivo para marcarlo en el registro.  
  
   - `defaultIcon`: Icono que se va a usar para este tipo de archivo. El icono debe agregarse como un recurso de archivo en el manifiesto de aplicación. Para obtener más información, vea [Cómo: Inclusión de un archivo de datos en una aplicación ClickOnce](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md).  
  
     Para obtener un ejemplo de `file` los `fileAssociation` elementos y, vea [ \<fileAssociation> Element](../deployment/fileassociation-element-clickonce-application.md).  
  
5. Si desea asociar más de un tipo de archivo a la aplicación, agregue `fileAssociation` elementos adicionales. Tenga en cuenta que el `progid` atributo debe ser diferente para cada.  
  
6. Una vez que haya terminado con el manifiesto de aplicación, vuelva a firmar el manifiesto. Puede hacerlo desde la línea de comandos mediante Mage.exe.  
  
    `mage -Sign WindowsFormsApp1.exe.manifest -CertFile mycert.pfx`  
  
    Para obtener más información, consulte [Mage.exe (herramienta de generación y edición de manifiestos)](https://msdn.microsoft.com/library/77dfe576-2962-407e-af13-82255df725a1) .  
  
## <a name="see-also"></a>Consulte también  
 [\<fileAssociation> Element](../deployment/fileassociation-element-clickonce-application.md)   
 [Manifiesto de aplicación ClickOnce](../deployment/clickonce-application-manifest.md)   
 [Mage.exe (Herramienta de generación y edición de manifiestos)](https://msdn.microsoft.com/library/77dfe576-2962-407e-af13-82255df725a1)
