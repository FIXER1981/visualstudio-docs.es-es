---
title: IDebugBeforeSymbolSearchEvent2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugBeforeSymbolSearchEvent2 interface
ms.assetid: 679fd7b1-765a-41a8-a046-63240c09a499
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4f563d8cd40a8c30542b1aa93fa22afc8d161a52
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56715145"
---
# <a name="idebugbeforesymbolsearchevent2"></a>IDebugBeforeSymbolSearchEvent2
El motor de depuración (DE) envía esta interfaz para el Administrador de depuración (SDM) para establecer el estado de sesión mensaje barra durante las cargas de símbolos.

## <a name="syntax"></a>Sintaxis

```
IDebugBeforeSymbolSearchEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Notas para los implementadores
 La DE implementa esta interfaz cuando el mensaje de la barra de estado se debe establecer durante la carga de símbolos. Esta interfaz se implementa únicamente por los motores de depuración que funcionan con o forman parte de los intérpretes de secuencia de comandos. El [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) interfaz debe implementarse en el mismo objeto que esta interfaz (usa el SDM **QueryInterface** para tener acceso a la **IDebugEvent2** interfaz).

## <a name="notes-for-callers"></a>Notas para los llamadores
 La DE crea y envía este objeto de evento cuando el mensaje de la barra de estado se debe establecer durante la carga de símbolos. El evento se envía mediante la [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) función de devolución de llamada proporcionada por el SDM cuando adjunta al programa que se está depurando.

## <a name="methods"></a>Métodos
 La tabla siguiente muestran los métodos de `IDebugBeforeSymbolSearchEvent2`.

|Método|Descripción|
|------------|-----------------|
|[GetModuleName](../../../extensibility/debugger/reference/idebugbeforesymbolsearchevent2-getmodulename.md)|Recupera el nombre del módulo que se está depurando actualmente.|

## <a name="requirements"></a>Requisitos
 Encabezado: Msdbg.h

 Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll