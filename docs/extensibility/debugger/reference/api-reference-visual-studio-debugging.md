---
title: Referencia de API (depuración de Visual Studio) | Documentos de Microsoft
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- debugging [Debugging SDK], API reference
ms.assetid: e4e429da-3667-41f7-9158-a8207d13e91a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7d415644897d7dd481f47c93a3b951db23fda843
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686358"
---
# <a name="api-reference-visual-studio-debugging"></a>Referencia de API (depuración de Visual Studio)
La sección de referencia incluye información general conceptual de la API, una guía que muestra la sintaxis y el uso para todos los elementos de la API y una gran variedad de ejemplos de código. Todas las referencias aparecen ordenadas alfabéticamente por categoría.

 En la tabla siguiente se muestra el común `HRESULT` valores devueltos por métodos.

|nombre|Descripción|Valor|
|----------|-----------------|-----------|
|S_OK|Correcto.|0x00000000|
|E_UNEXPECTED|Error inesperado.|0x8000FFFF|
|E_NOTIMPL|Sin implementar.|0x80004001|
|E_OUTOFMEMORY|No hay suficiente memoria para completar la operación.|0x8007000E|
|E_INVALIDARG|Uno o más argumentos no son válidos.|0x80070057|
|E_NOINTERFACE|No se admite dicha interfaz.|0x80004002|
|E_POINTER|Puntero no válido.|0x80004003|
|E_HANDLE|Identificador no válido.|0x80070006|
|E_ABORT|Operación anulada.|0x80004004|
|E_FAIL|Error inesperado.|0x80004005|
|E_ACCESSDENIED|Error de acceso general denegado.|0x80070005|

> [!NOTE]
>  Cuando un [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] depurar el método devuelve `S_OK`, se supone que todo punteros de parámetro son válidos, es decir, ninguna validación se lleva a cabo los punteros de parámetro cuando `S_OK` se devuelve.
>
> [!NOTE]
>  No válido o `NULL` [parámetros out] puede provocar que el IDE se bloquee.

## <a name="see-also"></a>Vea también
- [Interfaces](../../../extensibility/debugger/reference/interfaces-visual-studio-debugging.md)
- [Enumeraciones](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [Estructuras y uniones](../../../extensibility/debugger/reference/structures-and-unions.md)
- [Asistentes de SDK para la depuración](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)
- [Extensibilidad del depurador de Visual Studio](../../../extensibility/debugger/visual-studio-debugger-extensibility.md)