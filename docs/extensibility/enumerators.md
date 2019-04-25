---
title: Los enumeradores | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, enumerators
ms.assetid: a60030c5-e1d1-47e1-84bb-cbfe838ab479
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 37f469ecc0ae097592a128b30a6a6f189d58d94b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689751"
---
# <a name="enumerators"></a>Enumeradores
Esta sección enumeran los tipos de datos del enumerador en la API de complemento de Control de origen que debe conocer el complemento de control de código fuente.

## <a name="in-this-section"></a>En esta sección
- [Código de comando](../extensibility/command-code-enumerator.md) enumera las opciones para la [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md) y [SccPopulateList](../extensibility/sccpopulatelist-function.md) funciones.

- [Mensaje](../extensibility/message-enumerator.md) enumera los marcadores utilizados para la devolución de llamada impresión [LPTEXTOUTPROC](../extensibility/lptextoutproc.md).

- [Archivo de código de estado](../extensibility/file-status-code-enumerator.md) contiene valores constantes que especifican el estado de un archivo bajo control de código fuente con nombre.

- [Código de estado de directorio](../extensibility/directory-status-code-enumerator.md) contiene valores constantes que especifican el estado de un directorio bajo control de código fuente con nombre.

## <a name="related-sections"></a>Secciones relacionadas
- [Crear un control de código fuente complemento](../extensibility/internals/creating-a-source-control-plug-in.md) define el SDK de complemento de Control de origen y se describen los recursos incluidos.

- [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md) pide al usuario las opciones avanzadas para el comando especificado.

- [SccPopulateList](../extensibility/sccpopulatelist-function.md) examina la lista de archivos para su estado actual. Además, utiliza el `pfnPopulate` función para notificar al llamador cuando un archivo no coincide con los criterios para la `nCommand`.

- [LPTEXTOUTPROC](../extensibility/lptextoutproc.md) describe la función de devolución de llamada que se usa por [SccOpenProject](../extensibility/sccopenproject-function.md) para mostrar mensajes desde el complemento a través del IDE de control de origen.

- [Los complementos de control de origen](../extensibility/source-control-plug-ins.md) proporciona una lista completa de todos los elementos de la API de complemento de Control de código fuente.