---
title: Introducción al diagnóstico de gráficos | Microsoft Docs
ms.custom: seodec18
ms.date: 05/26/2017
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: eb651d9b35dd4531f4d14e169ab6f04376d4dfff
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72735703"
---
# <a name="getting-started-with-visual-studio-graphics-diagnostics"></a>Introducción al Diagnóstico de gráficos de Visual Studio
En esta sección se explicará cómo usar el diagnóstico de gráficos por primera vez, se capturarán fotogramas en una aplicación de Direct3D y se examinarán esos fotogramas en el Analizador de gráficos.

## <a name="requirements"></a>Requisitos
 Para usar Diagnóstico de gráficos en Visual Studio, debe usar Visual Studio Enterprise, Visual Studio Professional o Visual Studio Community.  Otras ediciones, incluidas Visual Studio Code, no contienen esta característica.

 [!INCLUDE[downloadvs](../includes/downloadvs_md.md)]

### <a name="windows-10-prerequisites"></a>Requisitos previos de Windows 10
 La característica opcional de Windows *Herramientas de gráficos* proporciona la infraestructura de captura y reproducción requerida por el Diagnóstico de gráficos de Windows 10.

 Para obtener información sobre cómo instalar las herramientas de gráficos, vea la sección [Instalación de las herramientas de gráficos para Windows 10](#InstallGraphicsTools).

## <a name="InstallGraphicsTools"></a> Instalación de las herramientas de gráficos para Windows 10
 En Windows 10, la infraestructura de diagnóstico de gráficos proporciona una característica opcional de Windows denominada *Herramientas de gráficos*. Esta característica es necesaria para capturar y reproducir información de gráficos en Windows 10 independientemente de si la aplicación capturada tiene como destino una versión anterior de Windows o de la versión de Direct3D que se use. Puede instalar previamente la característica de herramientas de gráficos o esperar e instalarla cuando se le solicite la primera vez que inicie una sesión de diagnóstico de gráficos desde Visual Studio.

#### <a name="to-install-graphics-tools-for-windows-10"></a>Para instalar las herramientas de gráficos para Windows 10

1. En buscar, escriba **aplicaciones y características** y, a continuación, abra la configuración **aplicaciones & características** .

2. En el lado derecho del cuadro de diálogo **aplicaciones & características** , elija **administrar características opcionales** (en **aplicaciones & características**).

   Aparece el cuadro de diálogo **Administrar características opcionales**.

3. En el cuadro de diálogo **Administrar características opcionales**, elija **Agregar una característica**. Aparece una lista de las características opcionales que se pueden instalar.

4. Seleccione **Herramientas de gráficos** en la lista de características y luego elija **Instalar**.

   La característica Herramientas de gráficos también se instala automáticamente al instalar el SDK de Windows 10.

> [!TIP]
> La característica opcional Herramientas de gráficos de Windows 10 proporciona la funcionalidad de captura y reproducción ligera (por ejemplo, el programa de captura de línea de comandos **dxcap.exe**) que se puede usar en escenarios de compatibilidad, pruebas y diagnóstico en máquinas donde no están instaladas las herramientas de desarrollador. Para obtener más información, vea el tema [Herramienta de captura de línea de comandos](command-line-capture-tool.md).

## <a name="using-graphics-diagnostics-for-the-first-time"></a>Usar el diagnóstico de gráficos por primera vez
 Ahora que tienen todo lo que necesita, ya puede empezar a usar el diagnóstico de gráficos. Tan solo tiene que seguir estos pasos:

### <a name="1---create-a-direct3d-app"></a>1: Crear una aplicación de Direct3D
 Si ya tiene su propia aplicación de Direct3D para explorar Diagnóstico de gráficos con, excelente. En caso contrario, utilice una de las siguientes opciones:

- Las plantillas de proyecto de la **aplicación DirectX 11 (Windows universal)** o de la **aplicación DirectX 12 (Windows universal)** para Windows 10.
- [Ejemplo de UAP de Direct3D 12](https://code.msdn.microsoft.com/Direct3D-12-UAP-Sample-ecb1779f) para Windows 10.

  Asegúrese de que puede compilar la aplicación antes de continuar.

### <a name="2---start-a-graphics-diagnostics-session"></a>2: Iniciar una sesión de diagnóstico de gráficos
 Ahora está listo para empezar la primera sesión de diagnóstico de gráficos. En Visual Studio, en el menú principal, elija **depurar, gráficos, iniciar depuración de gráficos**o simplemente presione **Alt + F5**. La aplicación se inicia en diagnóstico de gráficos y muestra las ventanas de sesión de diagnóstico en Visual Studio.

> [!IMPORTANT]
> Si está ejecutando la aplicación en Windows 10 y todavía no ha instalado la característica opcional de herramientas de gráficos, se le pedirá que lo haga ahora. Debe instalarla para poder usar el diagnóstico de gráficos en Windows 10.

### <a name="3---capture-frames"></a>3: Capturar fotogramas
 Una vez iniciada la aplicación, ya se pueden capturar fotogramas.

#### <a name="to-capture-single-frames"></a>Para capturar fotogramas individuales

- En Visual Studio, elija el botón **Capturar fotograma** en la barra de herramientas de gráficos o la ventana de sesión de diagnóstico. O bien, si la aplicación tiene el foco, solo tiene que presionar la tecla **Impr Pant** del teclado.

#### <a name="to-capture-a-sequence-of-frames"></a>Para capturar una secuencia de fotogramas

- En Visual Studio, en la ventana de la sesión de diagnóstico, establezca el **Número de fotogramas para capturar** en el número de fotogramas que quiera capturar en secuencia; a continuación, capture la secuencia mediante cualquiera de los métodos descritos anteriormente para capturar fotogramas individuales.

   Para volver a capturar fotogramas individuales, establezca **Número de fotogramas para capturar** en *1*.

  Cuando termine de capturar fotogramas, salga de la aplicación o elija el botón **Detener** en la barra de herramientas de gráficos o en la ventana de sesión de diagnóstico.

### <a name="4---examine-captured-frames-in-the-graphics-analyzer"></a>4: Examinar los fotogramas capturados en el Analizador de gráficos
 Ahora puede examinar los fotogramas que acaba de capturar. Para empezar a analizar un fotograma, elija el número del fotograma en la ventana de sesión de diagnóstico. El fotograma se abrirá en el **Analizador de gráficos**, donde puede usar las herramientas de Diagnóstico de gráficos para examinar cómo su aplicación usa Direct3D para localizar problemas de representación, o usar la herramienta **Análisis de fotogramas** para estudiar su rendimiento.

 Si seleccionó el fotograma equivocado en la ventana de la sesión de diagnóstico o desea examinar otro fotograma, puede seleccionar uno nuevo el Analizador de gráficos. En la pestaña **Destino de la representación** de la ventana de registro de gráficos, debajo de la imagen del destino de representación, expanda la **Lista de fotogramas** y, a continuación, elija otro fotograma para examinarlo.

 Para obtener más información sobre cómo usar las herramientas del analizador de gráficos juntas, vea los [ejemplos](graphics-diagnostics-examples.md).

## <a name="see-also"></a>Vea también
- [Gráficos de Direct3D 12](/windows/desktop/direct3d12/direct3d-12-graphics)