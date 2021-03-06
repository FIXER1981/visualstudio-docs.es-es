---
title: 'Cómo: depurar un motor de depuración personalizado | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, debugging
- debugging [Debugging SDK], custom debug engines
ms.assetid: df27a8d6-3938-45ff-b47f-b684e80b38a0
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: b7e710cec4536a5a1327580e56c60cb23ca36f4c
ms.sourcegitcommit: fb8babf5cd72f1fc2f97ffe4ad7b62d91f325f61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2020
ms.locfileid: "90842630"
---
# <a name="how-to-debug-a-custom-debug-engine"></a>Cómo: Depurar un motor de depuración personalizado
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Un tipo de proyecto inicia el motor de depuración (DE) desde el <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg.DebugLaunch%2A> método. Esto significa que el DE se inicia bajo el control de la instancia de que [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] controla el tipo de proyecto. Sin embargo, esa instancia de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] no puede depurar de. A continuación se indican los pasos para que pueda depurar su personalizado DE.  
  
> [!NOTE]
> : En el procedimiento "depuración de un motor de depuración personalizado", debe esperar a que se inicie el DE para poder adjuntarlo. Si coloca un cuadro de mensaje cerca del principio de que aparece cuando se inicia el DE, puede adjuntar en ese momento y, a continuación, borrar el cuadro de mensaje para continuar. De este modo, puede detectar todos los eventos.  
  
> [!WARNING]
> Debe tener instalada la depuración remota antes de intentar realizar los procedimientos siguientes. Vea [depuración remota](../../debugger/remote-debugging.md) para obtener más información.  
  
### <a name="debugging-a-custom-debug-engine"></a>Depurar un motor de depuración personalizado  
  
1. Inicie msvsmon.exe, el monitor de depuración remota.  
  
2. En el menú **herramientas** de msvsmon.exe, seleccione **Opciones** para abrir el cuadro de diálogo **Opciones** .  
  
3. Seleccione la opción "sin autenticación" y haga clic en **Aceptar**.  
  
4. Inicie una instancia de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] y abra el proyecto de personalizado.  
  
5. Inicie una segunda instancia de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] y abra el proyecto personalizado que inicia el de (para el desarrollo, normalmente se encuentra en el subárbol del registro experimental que se configura cuando se instala VSIP).  
  
6. En esta segunda instancia de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] , cargue un archivo de código fuente desde el proyecto personalizado e inicie el programa que se va a depurar. Espere unos instantes para permitir que se cargue el DE o espere hasta que se alcance un punto DE interrupción.  
  
7. En la primera instancia de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] (con su proyecto de), seleccione **asociar al proceso** en el menú **depurar** .  
  
8. En el cuadro de diálogo **asociar al proceso** , cambie el **transporte** a **remoto (solo nativo sin autenticación)**.  
  
9. Cambie el **calificador** al nombre de la máquina (Nota: hay un historial de entradas, por lo que debe escribir este nombre solo una vez).  
  
10. En la lista **procesos disponibles** , seleccione la instancia de de que se está ejecutando y haga clic en el botón **adjuntar** .  
  
11. Una vez cargados los símbolos en su de, coloque los puntos de interrupción en el código DE.  
  
12. Cada vez que detenga y reinicie el proceso de depuración, repita los pasos 6 a 10.  
  
### <a name="debugging-a-custom-project-type"></a>Depurar un tipo de proyecto personalizado  
  
1. Comience [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] en el subárbol del registro normal y cargue el proyecto de tipo de proyecto (es decir, el origen del tipo de proyecto, no una instancia de su tipo de proyecto).  
  
2. Abra las propiedades del proyecto y vaya a la página **depurar** . En el **comando**, escriba la ruta de acceso al [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE (de forma predeterminada, es *[unidad]* \Archivos de programa\Microsoft [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 8\Common7\IDE\devenv.exe).  
  
3. En el caso de los **argumentos de comando**, escriba `/rootsuffix exp` para el subárbol del registro experimental (creado cuando se instaló VSIP).  
  
4. Haga clic en **Aceptar** para aceptar los cambios.  
  
5. Presione F5 para iniciar el tipo de proyecto. Esto iniciará una segunda instancia de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] .  
  
6. Llegados a este punto, puede colocar los puntos de interrupción en el código fuente del tipo de proyecto.  
  
7. En la segunda instancia de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] , cargue o cree una nueva instancia del tipo de proyecto. Durante la carga o la creación, es posible que se alcancen los puntos de interrupción.  
  
8. Depure el tipo de proyecto.  
  
9. Si decide depurar el proceso de inicio de, puede realizar los pasos del procedimiento "depuración de un motor de depuración personalizado" para adjuntar a su desde después DE iniciarlo. Esto le proporcionará tres instancias de en [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ejecución: una para el origen de tipo de proyecto, una segunda para el tipo de proyecto con instancias y una tercera asociada a su de.  
  
## <a name="see-also"></a>Consulte también  
 [Creación de un motor de depuración personalizado](../../extensibility/debugger/creating-a-custom-debug-engine.md)
