---
title: Propiedades del depurador de Android (C++) | Microsoft Docs
ms.custom: ''
ms.date: 10/23/2017
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 789f7a1c-38b4-41d0-809b-14f4d96c8116
author: corob-msft
ms.author: corob
manager: jillfra
f1_keywords:
- VC.Project.AndroidDebugger.DebuggerType
- VC.Project.AndroidDebugger.AndroidDeviceID
- VC.Project.AndroidDebugger.PackagePath
- VC.Project.AndroidDebugger.LaunchActivity
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: 0a052223fe7acac87acf15c5c5091c774451e4e4
ms.sourcegitcommit: 6ae0a289f1654dec63b412bfa22035511a2ef5ad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2019
ms.locfileid: "71950631"
---
# <a name="android-debugger-properties"></a>Propiedades del depurador de Android

Propiedad. | DESCRIPCIÓN | Opciones
--- | ---| ---
Tipo de depurador | Especifica qué tipo de código se va a depurar. | **Solo nativo**<br>**Solo Java**<br>
Destino de depuración | Especifica el emulador o dispositivo que se usará para la depuración. Si no se ejecutan emuladores, use "Android Virtual Device (AVD) Manager" para iniciar un dispositivo.
Paquete que se iniciará | Especifica la ubicación del archivo *.apk* que se va a depurar. Elija esta opción para especificar que se debe iniciar un paquete (APK) específico cuando se depure la aplicación.
Actividad de inicio | La actividad de Android que se usará para iniciar la aplicación tiene que coincidir con la que se usa en el manifiesto. Presione Aplicar para recuperar la lista de *AndroidManifest.xml* y rellenarla de forma dinámica.
Rutas de búsqueda de símbolos adicionales | Ruta de búsqueda adicional para los símbolos de depuración.
Rutas de búsqueda de código fuente Java adicionales | Rutas de búsqueda adicional para los archivos de código fuente Java. Solo se aplica cuando el tipo de depurador es únicamente Java.
