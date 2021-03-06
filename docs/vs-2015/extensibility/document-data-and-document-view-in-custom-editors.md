---
title: Datos de documento y vista de documento en editores personalizados | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - document data and document view
ms.assetid: 71eea623-f566-4feb-84cd-ca1ba71bc493
caps.latest.revision: 24
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 2f73ffde43f2ef3608ae492a9643f7920243d818
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68204686"
---
# <a name="document-data-and-document-view-in-custom-editors"></a>Datos de documento y vista de documento en editores personalizados
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Un editor personalizado consta de dos partes: un objeto de datos de documento y un objeto de vista de documento. Como sugieren los nombres, el objeto de datos del documento representa los datos de texto que se van a mostrar y el objeto de vista del documento (o "vista") representa una o más ventanas en las que se va a mostrar el objeto de datos del documento.  
  
## <a name="document-data-object"></a>Objeto de datos de documento  
 Un objeto de datos de documento es una representación de datos de texto en el búfer de texto. Es un objeto COM que almacena el texto del documento y otra información, controla la persistencia del documento y habilita varias vistas de sus datos. Para obtener más información, vea  
  
 <xref:EnvDTE80.Window2.DocumentData%2A> y las [ventanas de documento](../extensibility/internals/document-windows.md).  
  
 Los editores y diseñadores personalizados pueden optar por usar el <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objeto o su propio búfer personalizado. <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> sigue el modelo de incrustación simplificado para un editor estándar, admite varias vistas y proporciona interfaces de eventos que se usan para administrar varias vistas.  
  
## <a name="document-view-object"></a>Objeto de vista de documento  
 Una ventana que muestra código y otro texto se conoce como vista o vista de documento. Al crear un editor, puede elegir una vista única, en la que el texto se muestra en una sola ventana o en una vista múltiple, en la que el texto se muestra en más de una ventana. Su elección depende de la aplicación. Por ejemplo, si necesita la edición en paralelo, debe elegir vista múltiple. Cada vista está asociada a una entrada en la tabla de documentos en ejecución (IDE) de entorno de desarrollo integrado (IDE). Las ventanas de la vista pertenecen a un proyecto o a un <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> objeto.  
  
 Si el editor admite varias vistas de un objeto de datos de documento, los datos de documento y los objetos de vista de documento deben ser independientes. De lo contrario, se pueden agrupar. Para obtener más información, vea [admitir varias vistas de documentos](../extensibility/supporting-multiple-document-views.md).  
  
 El IDE notifica a las vistas acerca de los eventos (por ejemplo, cuando se cierra una solución que contiene un documento) haciendo coincidir un identificador de elemento (ItemID) con cada entrada de la tabla de documentos en ejecución. Para obtener más información sobre esto, vea [ejecutar la tabla de documentos](../extensibility/internals/running-document-table.md).  
  
 Hay dos opciones para crear una vista para un editor personalizado. Uno es el modelo de activación en contexto, donde la vista se hospeda en una ventana con un control ActiveX o un objeto de datos de documento. El segundo es el modelo de incrustación simplificado, donde la vista se hospeda en [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] y <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> se implementa para controlar los comandos de la ventana. Para obtener información sobre el modelo de activación en contexto, consulte [activación en contexto](../misc/in-place-activation.md). Para obtener información sobre el modelo de incrustación simplificado, vea [incrustación simplificada](../extensibility/simplified-embedding.md).  
  
## <a name="see-also"></a>Consulte también  
 [Compatibilidad con varias vistas de documento](../extensibility/supporting-multiple-document-views.md)   
 [Incrustación simplificada](../extensibility/simplified-embedding.md)   
 [Cómo: adjuntar vistas a datos de documento](../extensibility/how-to-attach-views-to-document-data.md)   
 [Administración de titulares de bloqueo de documentos](../extensibility/document-lock-holder-management.md)   
 [Vistas de una y varias pestañas](../extensibility/single-and-multi-tab-views.md)   
 [Guardar un documento estándar](../extensibility/internals/saving-a-standard-document.md)   
 [Persistencia y la tabla de documentos en ejecución](../extensibility/internals/persistence-and-the-running-document-table.md)   
 [Determinar qué editor abre un archivo en un proyecto](../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md)   
 [Generadores del editor](../extensibility/editor-factories.md)
