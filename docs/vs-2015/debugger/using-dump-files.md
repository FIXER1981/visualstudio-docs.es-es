---
title: Usar archivos de volcado de memoria | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.crashdump
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- dumps, about dumps
- crash dumps
- dump files
- dumps
ms.assetid: b71be6dc-57e0-4730-99d2-b540a0863e49
caps.latest.revision: 56
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1a2d6215887512f2e0c1410688b2bc924dc1fe3a
ms.sourcegitcommit: a77158415da04e9bb8b33c332f6cca8f14c08f8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2020
ms.locfileid: "86387062"
---
# <a name="using-dump-files"></a>Uso de archivos de volcado de memoria
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Archivos de volcado de memoria con o sin montones; crear un archivo de volcado de memoria; abrir un archivo de volcado de memoria; buscar los archivos binarios, archivos pdb y el archivo de origen de un archivo de volcado de memoria. 
  
## <a name="contents"></a><a name="BKMK_Contents"></a> Contenido  
 [¿Qué es un archivo de volcado de memoria?](#BKMK_What_is_a_dump_file_)  
  
 [Archivos de volcado de memoria, con o sin montones](#BKMK_Dump_files__with_or_without_heaps)  
  
 [Requisitos y limitaciones](#BKMK_Requirements_and_limitations)  
  
 [Crear un archivo de volcado de memoria](#BKMK_Create_a_dump_file)  
  
 [Abrir un archivo de volcado de memoria](#BKMK_Open_a_dump_file)  
  
 [Buscar archivos binarios, de símbolos (.pdb) y de código fuente](#BKMK_Find_binaries__symbol___pdb__files__and_source_files)  
  
## <a name="what-is-a-dump-file"></a><a name="BKMK_What_is_a_dump_file_"></a>¿Qué es un archivo de volcado de memoria?  
 Un *archivo de volcado* de memoria es una instantánea de una aplicación en el momento en que se toma el volcado. Muestra qué proceso se ejecutaba y qué módulos se cargaron. Si el volcado de memoria se guardó con información de montón, el archivo de volcado de memoria contiene una instantánea de los datos que se encontraban en la memoria de la aplicación en ese momento. Abrir un archivo de volcado de memoria con un montón en Visual Studio es como detener en un punto de interrupción en una sesión de depuración. Aunque no puede continuar la ejecución, puede examinar las pilas, los subprocesos y los valores de las variables de la aplicación cuando se produjo el volcado de memoria.  
  
 Los volcados de memoria se utilizan principalmente para problemas de depuración que suceden en equipos a los que el desarrollador no tiene acceso. Por ejemplo, puede usar un archivo de volcado de memoria del equipo de un cliente cuando no pueda reproducir el bloqueo del cliente o el programa que no responde en la máquina. Los evaluadores también crean los volcados de memoria para guardar los datos de los programas bloqueados o que no responden, de modo que el equipo de pruebas pueda usarse para realizar más pruebas. El depurador de Visual Studio puede guardar archivos de volcado de memoria de código administrado o nativo. El depurador puede cargar archivos de volcado de memoria creados por Visual Studio u otros programas que guardan archivos en formato de *minivolcado* .  
  
 ![Volver al principio](../debugger/media/pcs-backtotop.png "PCS_BackToTop") [Contenido](#BKMK_Contents)  
  
## <a name="dump-files-with-or-without-heaps"></a><a name="BKMK_Dump_files__with_or_without_heaps"></a>Archivos de volcado de memoria, con o sin montones  
 Puede crear archivos de volcado de memoria con o sin información del montón.  
  
- **Los archivos de volcado de memoria con montones** contienen una instantánea de la memoria de la aplicación. Esto incluye los valores de las variables en el momento en que se creó el volcado de memoria. Si carga un archivo de volcado de memoria que se guardó con un montón, Visual Studio puede cargar los símbolos incluso si no se encuentra el archivo binario de la aplicación. Visual Studio también guarda los archivos binarios de los módulos nativos cargados en el archivo de volcado de memoria, lo que puede facilitar mucho más la depuración.  
  
- **Los archivos de volcado de memoria sin montones** son mucho más pequeños que los volcados con información de montón. Sin embargo, el depurador debe cargar los archivos binarios de aplicación para encontrar la información de símbolos. Los archivos binarios deben coincidir exactamente con los archivos binarios que se usaron al crear el volcado de memoria. Solo los valores de las variables de pila se guardan en los archivos de volcado de memoria sin datos de montón.  
  
  ![Volver al principio](../debugger/media/pcs-backtotop.png "PCS_BackToTop") [Contenido](#BKMK_Contents)  
  
## <a name="requirements-and-limitations"></a><a name="BKMK_Requirements_and_limitations"></a> Limitaciones y requisitos  
  
- La depuración de archivos de volcado de memoria de código optimizado puede resultar confusa. Por ejemplo, la inclusión en línea de funciones por parte del compilador puede dar lugar a pilas de llamadas inesperadas y otras optimizaciones podrían cambiar la duración de las variables.  
  
- Los archivos de volcado de memoria de equipos de 64 bits deben depurarse en una instancia de Visual Studio que se ejecute en un equipo de 64 bits.  
  
- En versiones de Visual Studio anteriores a VS 2013, los volcados de las aplicaciones de 32 bits que se ejecutaban en equipos de 64 bits recopilados por algunas herramientas (como el Administrador de tareas y WinDbg de 64 bits) no se podían abrir en Visual Studio. Esta limitación se ha eliminado en VS 2013.  
  
- Visual Studio puede depurar archivos de volcado de memoria de aplicaciones nativas desde dispositivos ARM. Visual Studio también puede depurar archivos de volcado de memoria de aplicaciones administradas desde dispositivos ARM pero solo en el depurador nativo.  
  
- Para depurar archivos de volcado en [modo kernel](https://msdn.microsoft.com/library/windows/hardware/ff551880.aspx) en Visual Studio 2013, descargue la [versión Windows 8.1 de las herramientas de depuración para Windows](https://msdn.microsoft.com/windows/hardware/gg463009). Consulte [depuración del kernel en Visual Studio](https://msdn.microsoft.com/library/windows/hardware/jj149675.aspx).  
  
- Visual Studio no puede depurar archivos de volcado de memoria guardados en el formato de volcado más antiguo conocido como un [volcado de modo de usuario completo](/windows-hardware/drivers/debugger/user-mode-dump-files#full). Tenga en cuenta que un volcado de memoria completo en modo usuario no es igual que un volcado de memoria con montón.  
  
- Para depurar con el [SOS.dll (extensión de depuración de SOS)](https://msdn.microsoft.com/library/9ac1b522-77ab-4cdc-852a-20fcdc9ae498) en Visual Studio, debe instalar las herramientas de depuración para Windows que forman parte de Windows Driver Kit (WDK). Vea [Windows 8.1 Preview: descargar kits, bits y herramientas](https://msdn.microsoft.com/library/windows/hardware/bg127147.aspx).  
  
  ![Volver al principio](../debugger/media/pcs-backtotop.png "PCS_BackToTop") [Contenido](#BKMK_Contents)  
  
## <a name="create-a-dump-file"></a><a name="BKMK_Create_a_dump_file"></a> Crear un archivo de volcado de memoria  
 Para crear un archivo de volcado de memoria con Visual Studio:  
  
- Mientras depura un proceso en Visual Studio, puede guardar un archivo de volcado de memoria cuando el depurador se ha detenido en una excepción o en un punto de interrupción. Elija **Guardar volcado como**, **depurar**. En el cuadro de diálogo **Guardar volcado como** , en la lista **Guardar como tipo** , puede seleccionar **minivolcado** o **minivolcado con montón** (valor predeterminado).  
  
- Con la [depuración Just-in-Time](../debugger/just-in-time-debugging-in-visual-studio.md) habilitada, puede adjuntar el depurador a un proceso bloqueado que se ejecute fuera del depurador y, a continuación, guardar un archivo de volcado de memoria. Vea [asociar a procesos en ejecución](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)  
  
  También puede crear archivos de volcado de memoria con cualquier programa que admita el formato de minivolcado de Windows. Por ejemplo, la utilidad de línea de comandos **Procdump** de [Windows Sysinternals](https://technet.microsoft.com/sysinternals/default) puede crear archivos de volcado de memoria de procesos basados en desencadenadores o a petición. Vea [los requisitos y las limitaciones](../debugger/using-dump-files.md#BKMK_Requirements_and_limitations) de este tema para obtener información adicional sobre cómo usar otras herramientas para crear archivos de volcado de memoria.  
  
  ![Volver al principio](../debugger/media/pcs-backtotop.png "PCS_BackToTop") [Contenido](#BKMK_Contents)  
  
## <a name="open-a-dump-file"></a><a name="BKMK_Open_a_dump_file"></a> Abrir un archivo de volcado de memoria  
  
1. En Visual Studio, elija **archivo**, **abrir**, **archivo**.  
  
2. En el cuadro de diálogo **Abrir archivo**, busque y seleccione el archivo de volcado de memoria. Normalmente, tendrá la extensión .dmp. Después, haga clic en **Aceptar**.  
  
3. Aparece la ventana **Resumen del archivo de volcado** . En esta ventana, puede ver información de resumen de depuración para el archivo de volcado de memoria, establecer la ruta de acceso de símbolos, iniciar la depuración y copiar la información de resumen en el portapapeles.  
  
     ![Página de resumen de minivolcado](../debugger/media/dbg-dump-summarypage.png "DBG_DUMP_SummaryPage")  
  
4. Para iniciar la depuración, vaya a la sección **acciones** y elija depurar **con solo nativo** o **depurar con mixto**.  
  
## <a name="find-binaries-symbol-pdb-files-and-source-files"></a><a name="BKMK_Find_binaries__symbol___pdb__files__and_source_files"></a>Buscar archivos binarios, de símbolos (. pdb) y de código fuente  
 Para utilizar todas las características de Visual Studio para depurar un archivo de volcado de memoria, necesita acceso a:  
  
- El archivo .exe para el que se ha realizado el volcado de memoria y otros archivos binarios (archivos DLL, etc.) usados en el proceso de volcado de memoria.  
  
   Si está depurando un volcado de memoria con datos del montón, Visual Studio puede solventar el problema de que falten archivos binarios de algunos módulos, pero debe tener archivos binarios para suficientes módulos para poder generar pilas de llamadas válidas. Visual Studio incluye los módulos nativos en un archivo de volcado de memoria con el montón.  
  
- Archivos de símbolos (.pdb) del archivo .exe y otros archivos binarios.  
  
- Archivos de código fuente de los módulos que le interesan.  
  
   El archivo ejecutable y los archivos .pdb deben coincidir exactamente con la versión y la compilación de los archivos utilizados en el momento en el que se creó el volcado de memoria.  
  
   Puede depurar utilizando el desensamblado de los módulos si no encuentra los archivos de código fuente.  
  
  **Rutas de acceso de búsqueda predeterminadas de los archivos ejecutables**  
  
  Visual Studio busca automáticamente en estas ubicaciones archivos ejecutables que no se incluyen en el archivo de volcado de memoria:  
  
1. Directorio que contiene el archivo de volcado de memoria.  
  
2. Ruta de acceso del módulo que se especifica en el archivo de volcado de memoria. Es la ruta de acceso del módulo en el equipo en el que se recopiló el volcado de memoria.  
  
3. Rutas de acceso de símbolos especificadas en la página **depuración**, **Opciones**, **símbolos** del cuadro de diálogo **herramientas**, **Opciones** de Visual Studio. Puede agregar más ubicaciones que desee buscar en esta página.  
  
   **Usar páginas no binarias / de símbolos/ de origen**  
  
   Si Visual Studio no puede encontrar los archivos necesarios para depurar un módulo en el volcado, muestra una página adecuada (**no se encontró ningún binario**, **no se encontraron símbolos**o **no se encontró ningún origen**). Estas páginas ofrecen información detallada acerca de la causa del problema y proporcionan vínculos de acción que pueden ayudarle a identificar la ubicación correcta de los archivos. Vea [especificar archivos de código fuente y símbolos (. pdb)](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
   ![Volver al principio](../debugger/media/pcs-backtotop.png "PCS_BackToTop") [Contenido](#BKMK_Contents)  
  
## <a name="see-also"></a>Consulte también  
 [Depuración Just-in-Time](../debugger/just-in-time-debugging-in-visual-studio.md)   
 [Especificar archivos de código fuente y símbolos (. pdb)](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [IntelliTrace](../debugger/intellitrace.md)
