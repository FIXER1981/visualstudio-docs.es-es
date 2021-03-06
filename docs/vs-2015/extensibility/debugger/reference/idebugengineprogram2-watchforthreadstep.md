---
title: 'IDebugEngineProgram2:: WatchForThreadStep | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugEngineProgram2::WatchForThreadStep
helpviewer_keywords:
- IDebugEngineProgram2::WatchForThreadStep
ms.assetid: b70922a3-1313-409a-b3b7-50c7cd13e394
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 59489af368c2e95a2d3cc93edbd6f7ab02a1c156
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "68195649"
---
# <a name="idebugengineprogram2watchforthreadstep"></a>IDebugEngineProgram2::WatchForThreadStep
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Inspecciona la ejecución (o deja de ver la ejecución) para que se produzca en el subproceso determinado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
HRESULT WatchForThreadStep(   
   IDebugProgram2* pOriginatingProgram,  
   DWORD           dwTid,  
   BOOL            fWatch,  
   DWORD           dwFrame  
);  
```  
  
```csharp  
int WatchForThreadStep(   
   IDebugProgram2 pOriginatingProgram,  
   uint           dwTid,  
   int            fWatch,  
   uint           dwFrame  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pOriginatingProgram`  
 de Un objeto [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) que representa el programa que se va a recorrer.  
  
 `dwTid`  
 de Especifica el identificador del subproceso que se va a inspeccionar.  
  
 `fWatch`  
 de Un valor distinto de cero ( `TRUE` ) significa que comienza la supervisión de la ejecución en el subproceso identificado por `dwTid` ; de lo contrario, cero () significa que se va a `FALSE` dejar de supervisar la ejecución en `dwTid` .  
  
 `dwFrame`  
 de Especifica un índice de marco que controla el tipo de paso. Cuando este valor es cero (0), el tipo de paso es "paso a paso por instrucciones" y el programa debe detenerse siempre que se ejecute el subproceso identificado por `dwTid` . Cuando `dwFrame` es distinto de cero, el tipo de paso es "paso a paso por procedimientos" y el programa solo debe detenerse si el subproceso identificado por `dwTid` se está ejecutando en un marco cuyo índice es igual o superior en la pila que `dwFrame` .  
  
## <a name="return-value"></a>Valor devuelto  
 Si la operación se realiza correctamente, devuelve `S_OK`; de lo contrario, devuelve un código de error.  
  
## <a name="remarks"></a>Comentarios  
 Cuando el administrador de depuración de sesión (SDM) realiza un programa, identificado por el `pOriginatingProgram` parámetro, notifica a todos los demás programas asociados llamando a este método.  
  
 Este método solo es aplicable al recorrido del mismo subproceso.  
  
## <a name="see-also"></a>Consulte también  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
