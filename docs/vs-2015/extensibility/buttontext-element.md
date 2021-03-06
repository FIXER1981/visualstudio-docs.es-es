---
title: ButtonText, elemento | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- ButtonText element (VSCT XML schema)
- VSCT XML schema elements, ButtonText
ms.assetid: 56aba884-0356-4894-ae4e-32d3938f6865
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ef22471d20df5582fec96c8a685029a1d475a4a4
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68184574"
---
# <a name="buttontext-element"></a>ButtonText (Elemento)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Este campo le permite especificar el texto que aparece en varios menús. De forma predeterminada, el `ButtonText` elemento aparece en los controladores de menús. El `ButtonText` elemento también se convierte en el valor predeterminado si los demás campos de texto están en blanco. El `ButtonText` elemento no puede estar en blanco ni siquiera si se especifican los demás campos de texto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
<ButtonText>My Command</ButtonText>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[Elemento Strings](../extensibility/strings-element.md)|Agrupa los elementos de texto, como `ButtonText` y `CommandName` .|  
  
## <a name="text-value"></a>Valor de texto  
 El valor de texto del `ButtonText` elemento proporciona el texto que se muestra para los elementos de menú, los cuadros combinados y otros elementos de la interfaz de usuario que tienen texto visible.  
  
## <a name="see-also"></a>Consulte también  
 [Archivos de tabla de comandos de Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
