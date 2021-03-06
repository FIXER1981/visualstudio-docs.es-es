---
title: para habilitar o deshabilitar Editar y continuar | Microsoft Docs
ms.custom: seodec18
ms.date: 10/04/2018
ms.topic: how-to
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- /INCREMENTAL linker option
- Apply Code Changes command
- Edit and Continue, disabling
- code changes, applying in break mode
- INCREMENTAL linker option
- Edit and Continue, enabling
- break mode, applying code changes
- Edit and Continue, applying code changes
- Step command
- Go command
ms.assetid: fd961a1c-76fa-420d-ad8f-c1a6c003b0db
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
- cplusplus
ms.openlocfilehash: ce531a0f7f9d6e26db38b5cf041f06d42209261a
ms.sourcegitcommit: 062615c058d2ff44751e8d0c704ccfa3c5543469
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90851403"
---
# <a name="how-to-enable-and-disable-edit-and-continue-c-vb-c"></a>Procedimiento para habilitar o deshabilitar Editar y continuar (C#, VB y C++)

En tiempo de diseño, puede deshabilitar o habilitar **Editar y continuar** en el cuadro de diálogo **Opciones** de Visual Studio. **Editar y continuar** solo funciona en las compilaciones de depuración. Para obtener más información, vea [Editar y continuar](../debugger/edit-and-continue.md).

En C++ nativo, **Editar y continuar** requiere el uso de la opción `/INCREMENTAL`. Para obtener más información sobre los requisitos de esta característica en C++, consulte esta [entrada de blog](https://devblogs.microsoft.com/cppblog/c-edit-and-continue-in-visual-studio-2015-update-3/), así como [Editar y continuar (C++)](../debugger/edit-and-continue-visual-cpp.md).

**Para habilitar o deshabilitar Editar y continuar:**

1. Si está en una sesión de depuración, detenga la depuración (**Depurar** > **Detener depuración** o **Mayús**+**F5**).

1. En **Herramientas** > **Opciones** > (o **Depurar** > **Opciones**) > **Depuración** > **General**, seleccione **Editar y continuar** en el panel derecho.

    > [!NOTE]
    > Si se habilita IntelliTrace y se recopilan eventos de IntelliTrace e información de llamadas, se deshabilita Editar y continuar. Para obtener más información, consulte [IntelliTrace](../debugger/intellitrace.md).

1. Para el código de C++, asegúrese de seleccionar **Habilitar la opción Editar y continuar nativa** y establezca estas opciones adicionales:
    - **Aplicar cambios al continuar (solo nativo)**

      Si se selecciona, Visual Studio compila y aplica automáticamente los cambios en el código al continuar con la depuración desde un estado de interrupción. De lo contrario, puede elegir aplicar los cambios mediante **Depuración** > **Aplicar cambios de código**.

    - **Advertir sobre el código obsoleto (solo nativo)**

      Si se selecciona, genera advertencias sobre el código obsoleto.

1. Haga clic en **Aceptar**.
