---
title: 'Cómo: abrir editores estándar | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], opening
- projects [Visual Studio SDK], opening standard editors
ms.assetid: d5ce10f9-047a-4b74-aa1d-295128898b89
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 792ac8a0859481fd97b2eaee4bd66753f0460a37
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68204134"
---
# <a name="how-to-open-standard-editors"></a>Apertura de editores estándar
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Al abrir un editor estándar, permite que el IDE determine un editor estándar para un tipo de archivo designado, en lugar de especificar un editor específico del proyecto para el archivo.  
  
 Complete el siguiente procedimiento para implementar el <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> método. Se abrirá un archivo de proyecto en un editor estándar.  
  
### <a name="to-implement-the-openitem-method-with-a-standard-editor"></a>Para implementar el método OpenItem con un editor estándar  
  
1. Llame <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable> `RDT_EditLock` a () para determinar si el archivo de objeto de datos del documento ya está abierto.  
  
2. Si el archivo ya está abierto, vuelva a exponer el archivo llamando al <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A> método, especificando un valor de `IDO_ActivateIfOpen` para el `grfIDO` parámetro.  
  
     Si el archivo está abierto y el documento es propiedad de un proyecto diferente del proyecto que realiza la llamada, el proyecto recibe una advertencia que indica que el editor que se está abriendo procede de otro proyecto. La ventana de archivo se Surface.  
  
3. Si el documento no está abierto o no está en la tabla de documentos en ejecución, llame al <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> método ( `OSE_ChooseBestStdEditor` ) para abrir un editor estándar para el archivo.  
  
     Cuando se llama al método, el IDE realiza las siguientes tareas:  
  
    1. El IDE examina la subclave de los editores/{guidEditorType}/Extensions en el registro para determinar qué editor puede abrir el archivo y tiene la prioridad más alta.  
  
    2. Una vez que el IDE ha determinado qué editor puede abrir el archivo, el IDE llama a <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> . La implementación del editor de este método devuelve información necesaria para que el IDE llame a <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateDocumentWindow%2A> y al sitio recién abierto.  
  
    3. Por último, el IDE carga el documento mediante la interfaz de persistencia habitual, como <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> .  
  
    4. Si el IDE ha determinado previamente que la jerarquía o el elemento de la jerarquía está disponible, el IDE llama al <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.GetItemContext%2A> método en el proyecto para obtener un puntero de contexto de nivel de proyecto <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> que se va a devolver con la <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateDocumentWindow%2A> llamada al método.  
  
4. Devuelve un <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> puntero al IDE cuando el IDE llama a <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.GetItemContext%2A> en el proyecto si desea permitir que el editor obtenga el contexto del proyecto.  
  
     La realización de este paso permite al proyecto ofrecer servicios adicionales al editor.  
  
     Si el objeto vista de documento o vista de documento se situó correctamente en un marco de ventana, el objeto se inicializa con sus datos mediante una llamada a <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.LoadDocData%2A> .  
  
## <a name="see-also"></a>Consulte también  
 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>   
 [Abrir y guardar elementos de proyecto](../extensibility/internals/opening-and-saving-project-items.md)   
 [Cómo: abrir editores específicos del proyecto](../extensibility/how-to-open-project-specific-editors.md)   
 [Cómo: abrir editores para documentos abiertos](../extensibility/how-to-open-editors-for-open-documents.md)   
 [Visualización de archivos mediante el comando Abrir archivo](../extensibility/internals/displaying-files-by-using-the-open-file-command.md)
