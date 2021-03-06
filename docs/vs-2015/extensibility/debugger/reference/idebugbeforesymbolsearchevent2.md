---
title: IDebugBeforeSymbolSearchEvent2 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugBeforeSymbolSearchEvent2 interface
ms.assetid: 679fd7b1-765a-41a8-a046-63240c09a499
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 26a8d7b28528a79a925207e1ee3794fcbb4ca1d2
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "62423522"
---
# <a name="idebugbeforesymbolsearchevent2"></a>IDebugBeforeSymbolSearchEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

El motor DE depuración (DE) envía esta interfaz al administrador de depuración de la sesión (SDM) para establecer el mensaje de la barra de estado durante las cargas de símbolos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
IDebugBeforeSymbolSearchEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Notas para los implementadores  
 El DE implementa esta interfaz cuando debe establecer el mensaje DE la barra de estado durante las cargas de símbolos. Esta interfaz la implementa solo los motores de depuración que funcionan con o forman parte de los intérpretes de script. La interfaz [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) debe implementarse en el mismo objeto que esta interfaz (el SDM usa **QueryInterface** para tener acceso a la interfaz **IDebugEvent2** ).  
  
## <a name="notes-for-callers"></a>Notas para llamadores  
 El DE crea y envía este objeto DE evento cuando debe establecer el mensaje DE la barra de estado durante las cargas de símbolos. El evento se envía mediante la función de devolución de llamada [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) proporcionada por el SDM cuando se adjunta al programa que se está depurando.  
  
## <a name="methods"></a>Métodos  
 En la tabla siguiente se muestran los métodos de `IDebugBeforeSymbolSearchEvent2` .  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetModuleName](../../../extensibility/debugger/reference/idebugbeforesymbolsearchevent2-getmodulename.md)|Recupera el nombre del módulo que se está depurando actualmente.|  
  
## <a name="requirements"></a>Requisitos  
 Encabezado: Msdbg. h  
  
 Espacio de nombres: Microsoft. VisualStudio. Debugger. Interop  
  
 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll
