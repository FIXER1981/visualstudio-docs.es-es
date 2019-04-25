---
title: Detalles de tiempo de ejecución del Control de origen | Documentos de Microsoft
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], runtime details
ms.assetid: 1acd30e0-f98c-4bde-b9cd-4076845887df
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3f7501a25596fc0a818277d164337bb0d4e4e077
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56618801"
---
# <a name="source-control-runtime-details"></a>Detalles de tiempo de ejecución del control de código fuente
Cuando el usuario agrega un archivo en el proyecto de control de código fuente, o a través de un controlador de automatización, como un asistente, se agrega un proyecto al control de código fuente. Un proyecto no especifica por sí mismo que está bajo control de código fuente; admite el control de código fuente, pero deben agregarse manualmente a él.

## <a name="registering-with-a-source-control-package"></a>Registro con un paquete de Control de código fuente
 Cuando se agrega un archivo en el proyecto de control de código fuente, el entorno llama a <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A> para proporcionar cuatro cadenas opacas que sirven como cookies por el sistema de control de código fuente. Store estas cadenas en el archivo de proyecto. Estas cadenas se deben pasar al código auxiliar de Control de origen (el componente de Visual Studio que administra los paquetes de control de origen) en el inicio del tipo de proyecto mediante una llamada a <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>. Esto a su vez carga el paquete de control de origen adecuado y reenvía la llamada a su implementación de `IVsSccManager2::RegisterSccProject`.

## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A>
- [Compatibilidad con control de código fuente](../../extensibility/internals/supporting-source-control.md)