---
title: IDebugPort2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPort2
helpviewer_keywords:
- IDebugPort2 interface
ms.assetid: 8fd87f05-a950-4d14-b925-98be29d4facc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 14c21b4f1546b262fb61c0da3ea95adee2aef8fa
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56687424"
---
# <a name="idebugport2"></a>IDebugPort2
Esta interfaz representa un puerto de depuración en un equipo.

## <a name="syntax"></a>Sintaxis

```
IDebugPort2 : IUnknown
```

## <a name="notes-for-implementers"></a>Notas para los implementadores
 Un proveedor de puerto personalizado implementa esta interfaz para representar un puerto de depuración en un equipo.

 Si el puerto es compatible con los eventos de puerto de envío, también debe implementar la <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> interfaz para admitir un <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> interfaz que proporciona a su vez la [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md) interfaz.

## <a name="notes-for-callers"></a>Notas para los llamadores
 Las llamadas a [GetPort](../../../extensibility/debugger/reference/idebugportsupplier2-getport.md) o [agregar puerto](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) devolver esta interfaz, que representa el puerto solicitado.

## <a name="methods-in-vtable-order"></a>Métodos en orden de Vtable
 La tabla siguiente muestran los métodos de `IDebugPort2`.

|Método|Descripción|
|------------|-----------------|
|[GetPortName](../../../extensibility/debugger/reference/idebugport2-getportname.md)|Devuelve el nombre del puerto.|
|[GetPortId](../../../extensibility/debugger/reference/idebugport2-getportid.md)|Devuelve el identificador de puerto.|
|[GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)|Devuelve la solicitud utilizada para crear un puerto (si está disponible).|
|[GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)|Devuelve el proveedor del puerto para este puerto.|
|[GetProcess](../../../extensibility/debugger/reference/idebugport2-getprocess.md)|Devuelve una interfaz para el proceso de identificador del proceso.|
|[EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)|Enumera todos los procesos que se ejecutan en un puerto.|

## <a name="remarks"></a>Comentarios
 El puerto local proporciona acceso a todos los procesos y los programas que se ejecutan en el equipo local. Otros puertos podrían representar una conexión de cable serie a un dispositivo basado en Windows CE o una conexión de red a un equipo que no son de DCOM. El `IDebugPort2` interfaz se usa para buscar el nombre y el identificador de un puerto y enumerar todos los procesos que se ejecutan en el puerto. Instalaciones para iniciar y detener procesos en el puerto se implementan en el `IDebugPortEx2` interfaz.

## <a name="requirements"></a>Requisitos
 Encabezado: msdbg.h

 Espacio de nombres:  Microsoft.VisualStudio.Debugger.Interop

 Ensamblado: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Vea también
- [Interfaces básicas](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)
- [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)