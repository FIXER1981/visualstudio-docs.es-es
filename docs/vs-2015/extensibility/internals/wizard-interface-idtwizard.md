---
title: Interfaz del asistente (IDTWizard) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDTWizard interface
- wizards, interface
ms.assetid: 09618d9d-d115-45b6-bccc-de328994b39c
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 78867fa94851e373ae4d47cd82cd1084a941638c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68180351"
---
# <a name="wizard-interface-idtwizard"></a>Interfaz de asistente (IDTWizard)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

El entorno de desarrollo integrado (IDE) utiliza la <xref:EnvDTE.IDTWizard> interfaz para comunicarse con los asistentes. Los asistentes deben implementar esta interfaz para poder instalarse en el IDE.  
  
 El <xref:EnvDTE.IDTWizard.Execute%2A> método es el único método asociado a la <xref:EnvDTE.IDTWizard> interfaz. Los asistentes implementan este método y el IDE llama al método en la interfaz. En el ejemplo siguiente se muestra la firma del método.  
  
```  
/* IDTWizard Method */  
STDMETHOD(Execute)(THIS_  
   /* [in] */ IDispatch *Application,  
   /* [in] */ long hwndOwner,  
   /* [in] */ SAFEARRAY * *ContextParams,  
   /* [in] */ SAFEARRAY * *CustomParams,  
   /* [out] [in] */ wizardResult *RetVal  
   );  
```  
  
 El mecanismo de inicio es similar para los asistentes **nuevo proyecto** y **Agregar nuevo elemento**. Para iniciar cualquiera de ellos, debe llamar a la <xref:EnvDTE.IDTWizard> interfaz definida en Dteinternal. h. La única diferencia es el conjunto de parámetros personalizados y de contexto que se pasan a la interfaz cuando se llama a la interfaz.  
  
 La siguiente información describe la <xref:EnvDTE.IDTWizard> interfaz que los asistentes deben implementar para trabajar en el [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE. El IDE llama al <xref:EnvDTE.IDTWizard.Execute%2A> método en el asistente y lo pasa a lo siguiente:  
  
- El objeto DTE  
  
     El objeto DTE es la raíz del modelo de automatización.  
  
- Identificador del cuadro de diálogo de la ventana, tal como se muestra en el segmento de código, `hwndOwner ([in] long)` .  
  
     El asistente lo usa `hwndOwner` como elemento primario para el cuadro de diálogo del asistente.  
  
- Parámetros de contexto que se pasan a la interfaz como variante para SAFEARRAY, tal como se muestra en el segmento de código `[in] SAFEARRAY (VARIANT)* ContextParams` .  
  
     Los parámetros de contexto contienen una matriz de valores que son específicos del tipo de asistente que se está iniciando y el estado actual del proyecto. El IDE pasa los parámetros de contexto al asistente. Para obtener más información, vea [parámetros de contexto](../../extensibility/internals/context-parameters.md).  
  
- Los parámetros personalizados que se pasan a la interfaz como una variante de SAFEARRAY, tal como se muestra en el segmento de código, `[in] SAFEARRAY (VARIANT)* CustomParams` .  
  
     Los parámetros personalizados contienen una matriz de parámetros definidos por el usuario. Un archivo. vsz pasa los parámetros personalizados al IDE. Los valores se determinan mediante las `Param=` instrucciones. Para obtener más información, vea [Custom Parameters](../../extensibility/internals/custom-parameters.md).  
  
- Los valores devueltos para la interfaz son  
  
    ```  
    wizardResultSuccess = -1,  
    wizardResultFailure = 0  
    wizardResultCancel = 1  
    wizardResultBackout = 2  
    ```  
  
## <a name="see-also"></a>Consulte también  
 [Parámetros de contexto](../../extensibility/internals/context-parameters.md)   
 [Parámetros personalizados](../../extensibility/internals/custom-parameters.md)   
 [Asistentes](../../extensibility/internals/wizards.md)   
 [Archivo de asistente (.Vsz)](../../extensibility/internals/wizard-dot-vsz-file.md)
