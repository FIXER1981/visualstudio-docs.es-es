---
title: Nueva experiencia de Git en Visual Studio (versión preliminar)
titleSuffix: ''
description: Más información sobre la nueva experiencia integrada de Git en Visual Studio 2019
ms.date: 09/22/2020
ms.topic: conceptual
ms.author: tglee
author: prnadago
ms.manager: jillfra
monikerRange: vs-2019
ms.openlocfilehash: 1f9dc891219e5563ad6ea72085b0ad28469c7171
ms.sourcegitcommit: a876fcc75321f9c30729121cae83f400973f9d9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2020
ms.locfileid: "92082062"
---
# <a name="new-git-experience-in-visual-studio-preview"></a>Nueva experiencia de Git en Visual Studio (versión preliminar)

A partir de la [versión 16.6](/visualstudio/releases/2019/release-notes-v16.6), Visual Studio 2019 incluye ahora una nueva experiencia de Git que facilita el uso de Git desde el IDE. Git es el sistema de control de versiones moderno más usado, por lo que no importa si es un desarrollador profesional o si está aprendiendo a codificar, Git puede resultarle muy útil.

> [!TIP]
> Si no está familiarizado con Git, el sitio web de https://git-scm.com/ es un buen punto de partida. Allí encontrará un libro en línea conocido, vídeos de conceptos básicos de Git y hojas de referencia rápida.

## <a name="how-to-start-using-git-in-visual-studio"></a>Inicio con Git en Visual Studio

Para cambiar a la nueva experiencia de Git, vaya a **Herramientas** > **Opciones** > **Entorno** > **Características en versión preliminar** y active la casilla **New Git User Experience** (Nueva experiencia de usuario de Git).

:::image type="content" source="media/git-opt-new-user-experience.png" alt-text="Captura de pantalla de la sección Características en versión preliminar del cuadro de diálogo Opciones de Visual Studio":::

Hay tres maneras de usar Git en Visual Studio 2019:

- [Apertura de un repositorio de Git existente](#open-an-existing-local-repository). Si el código ya está en la máquina, puede abrirlo mediante **Archivo** > **Abrir** > **Proyecto o solución** (o **Carpeta** ) y Visual Studio detectará automáticamente si tiene un repositorio de Git inicializado.
- [Creación de un repositorio Git](#create-a-new-git-repository). Si el código no está asociado a Git, puede crear un repositorio de Git.
- [Clonación de un repositorio de Git existente](#clone-an-existing-git-repository). Si el código en el que quiere trabajar no está en la máquina, puede clonar repositorios remotos existentes.

## <a name="create-a-new-git-repository"></a>Creación de un repositorio Git

Si el código no está asociado a Git, puede empezar por crear un repositorio de Git. Para ello, seleccione **GIT** > **Crear repositorio GIT** en la barra de menús. A continuación, en el cuadro de diálogo **Crear un repositorio GIT** , escriba su información.

:::image type="content" source="media/git-create-repository.png" alt-text="Captura de pantalla de la sección Características en versión preliminar del cuadro de diálogo Opciones de Visual Studio":::

El cuadro de diálogo **Crear un repositorio GIT** facilita la inserción del nuevo repositorio en GitHub. De forma predeterminada, el nuevo repositorio es privado, lo que significa que usted es el único que puede acceder a él. Si desactiva la casilla, el repositorio será público, lo que significa que cualquier persona en GitHub podrá verlo.

> [!TIP]
> Tanto si el repositorio es público como privado, es mejor tener una copia de seguridad remota del código almacenada de forma segura en GitHub, aunque no esté trabajando con un equipo. Así también tendrá el código a su disposición independientemente de la máquina que use.

Puede optar por crear un repositorio de Git solo local mediante la opción **Solo locales** . También puede vincular el repositorio con un repositorio remoto vacío existente en cualquier otro proveedor de Git mediante la opción **Existing remote** (Remoto existente).

## <a name="clone-an-existing-git-repository"></a>Clonación de un repositorio de Git existente

Visual Studio incluye una experiencia de clonación sencilla. Si conoce la dirección URL del repositorio que quiere clonar, puede pegar la dirección URL en la sección **Ubicación del repositorio** y luego elegir la ubicación del disco en la que quiere que Visual Studio se clone.

:::image type="content" source="media/git-clone-repository.png" alt-text="Captura de pantalla de la sección Características en versión preliminar del cuadro de diálogo Opciones de Visual Studio":::

Si no conoce la dirección URL del repositorio, Visual Studio facilita la búsqueda y clonación del repositorio existente de GitHub o Azure DevOps.

### <a name="open-an-existing-local-repository"></a>Apertura de un repositorio de Git existente

Después de clonar un repositorio o de crear uno, Visual Studio detecta el repositorio de Git y lo agrega a la lista de **repositorios locales** en el menú de Git. Desde aquí, puede acceder rápidamente a los repositorios de Git y cambiar de uno a otro.

:::image type="content" source="media/git-local-repositories.png" alt-text="Captura de pantalla de la sección Características en versión preliminar del cuadro de diálogo Opciones de Visual Studio":::

## <a name="view-files-in-solution-explorer"></a>Vista de archivos en el Explorador de soluciones

Al clonar un repositorio o abrir un repositorio local, Visual Studio lo lleva a ese contexto de Git al guardar y cerrar cualquier solución y proyecto abiertos previamente. El Explorador de soluciones carga la carpeta en la raíz del repositorio de Git y examina el árbol de directorios en busca de cualquier archivo de Vista. Estos incluyen archivos tales como CMakeLists.txt o aquellos que tienen la extensión de archivo .sln.

Visual Studio ajusta su Vista en función del archivo de Vista que se cargue en el Explorador de soluciones:

- Si clona un repositorio que contiene un solo archivo .sln, el Explorador de soluciones carga automáticamente esa solución.
- Si el Explorador de soluciones no detecta ningún archivo .sln en el repositorio, de forma predeterminada carga la Vista de carpetas.
- Si el repositorio tiene más de un archivo .sln, el Explorador de soluciones muestra la lista de Vistas disponibles para que pueda elegir una.

Puede alternar entre la Vista abierta actualmente y la lista de Vistas mediante el botón **Cambiar de vista** de la barra de herramientas del Explorador de soluciones.

:::image type="content" source="media/git-solution-explorer-views.png" alt-text="Captura de pantalla de la sección Características en versión preliminar del cuadro de diálogo Opciones de Visual Studio":::

## <a name="git-changes-window"></a>Ventana Cambios de Git

Git realiza un seguimiento de los cambios de archivo en el repositorio mientras usted trabaja y separa los archivos del repositorio en tres categorías. Estos cambios son equivalentes a lo que se vería al escribir el comando `git status` en la línea de comandos:

- **Archivos sin modificar** : Estos archivos no han cambiado desde la última confirmación.
- **Archivos modificados** : Estos archivos incluyen cambios realizados desde la última confirmación, pero aún no se han almacenado provisionalmente para la siguiente confirmación.
- **Archivos almacenados provisionalmente** : Estos archivos tienen cambios que se agregarán a la siguiente confirmación.

Mientras usted realiza su trabajo, Visual Studio realiza un seguimiento de los cambios de archivo en el proyecto en la sección **Cambios** de la ventana **Cambios de Git** .

:::image type="content" source="media/git-changes-window.png" alt-text="Captura de pantalla de la sección Características en versión preliminar del cuadro de diálogo Opciones de Visual Studio":::

Cuando esté listo para almacenar provisionalmente los cambios, haga clic en el botón **+** (más) en cada archivo que quiera almacenar provisionalmente o haga clic con el botón derecho en un archivo y seleccione **Agregar al "stage"** . También puede almacenar provisionalmente todos los archivos modificados con un solo clic mediante el botón **+** (más) de Almacenar todo provisionalmente situado en la parte superior de la sección **Cambios** .

Al almacenar provisionalmente un cambio, Visual Studio crea una sección **Cambios almacenados provisionalmente** . Solo se agregan en la siguiente confirmación los cambios de la sección **Cambios almacenados provisionalmente** , lo que puede hacer seleccionando **Confirmar almacenados provisionalmente** . También se pueden deshacer los cambios almacenados provisionalmente haciendo clic en el botón **–** (menos). El comando equivalente para esta acción es `git commit -m "Your commit message"`.

También puede optar por no almacenar provisionalmente los archivos modificados omitiendo el almacenamiento provisional. En este caso, Visual Studio le permite confirmar los cambios directamente sin tener que almacenarlos provisionalmente. Solo tiene que escribir el mensaje de confirmación y luego seleccionar **Confirmar todo** . El comando equivalente para esta acción es `git commit -a`.

Visual Studio también facilita la confirmación y sincronización con un solo clic mediante los métodos abreviados **Confirmar todo e insertar** y **Confirmar todo y sincronizar** . Al hacer doble clic en cualquier archivo de las secciones sección **Cambios** y **Cambios almacenados provisionalmente** , puede ver una comparación línea a línea con la versión no modificada del archivo.

:::image type="content" source="media/git-file-version-compare.png" alt-text="Captura de pantalla de la sección Características en versión preliminar del cuadro de diálogo Opciones de Visual Studio" si está conectado al repositorio de Azure DevOps. Puede conectar el repositorio de Azure DevOps mediante Team Explorer > Administrar conexiones.

### <a name="select-an-existing-branch"></a>Seleccione una rama existente:

Visual Studio muestra la rama actual en el selector situado en la parte superior de la ventana **Cambios de Git** .

:::image type="content" source="media/git-changes-current-branch-selector.png" alt-text="Captura de pantalla de la sección Características en versión preliminar del cuadro de diálogo Opciones de Visual Studio":::

La rama actual también está disponible en la barra de estado en la esquina inferior derecha del IDE de Visual Studio.

:::image type="content" source="media/git-changes-current-branch-status-bar.png" alt-text="Captura de pantalla de la sección Características en versión preliminar del cuadro de diálogo Opciones de Visual Studio":::

En ambas ubicaciones, puede alternar entre las ramas existentes.

### <a name="create-a-new-branch"></a>Creación de una rama

También puede crear una rama. El comando equivalente para esta acción es `git checkout <branchname>`.

La creación de una rama es tan sencillo como escribir el nombre de la rama y basarla en una rama existente.

:::image type="content" source="media/git-changes-create-new-branch.png" alt-text="Captura de pantalla de la sección Características en versión preliminar del cuadro de diálogo Opciones de Visual Studio":::

Puede elegir una rama local o remota existente como base. La casilla **Desproteger rama** le lleva automáticamente a la rama recién creada. El comando equivalente para esta acción es `git checkout -b <new-branch><existing-branch>`.

## <a name="git-repository-window"></a>Ventana Repositorio de GIT

Visual Studio tiene una nueva ventana **Repositorio de GIT** , que es una vista consolidada de todos los detalles del repositorio, incluidas todas las ramas, los elementos remotos y los historiales de confirmación. Puede acceder a esta ventana directamente desde **Git** o **Vista** en la barra de menús o desde la barra de estado.

### <a name="manage-branches"></a>Administración de ramas

Al seleccionar **Administrar ramas** en el menú **Git** , verá la vista de árbol Ramas en la ventana **Repositorio de GIT** . En el panel izquierdo, puede usar el menú contextual para desproteger ramas, crear ramas, combinar, fusionar mediante cambio de base, selección exclusiva, etc. Al hacer clic en la rama, puede ver una vista previa del historial de confirmaciones en el panel derecho.

### <a name="incoming-and-outgoing-commits"></a>Confirmaciones entrantes y salientes

Al capturar una rama, la ventana **Cambios de Git** presenta un indicador en la lista desplegable Rama, que muestra el número de confirmaciones no extraídas de la rama remota. Este indicador también muestra el número de confirmaciones locales sin insertar.

:::image type="content" source="media/git-repo-drop-down-indicator.png" alt-text="Captura de pantalla de la sección Características en versión preliminar del cuadro de diálogo Opciones de Visual Studio":::

El indicador también funciona como un vínculo que le lleva al historial de confirmaciones de esa rama en la ventana **Repositorio de GIT** . En la parte superior del historial se muestran los detalles de estas confirmaciones entrantes y salientes. Desde aquí, también puede optar por extraer o insertar las confirmaciones.

:::image type="content" source="media/git-branch-commit-history.png" alt-text="Captura de pantalla de la sección Características en versión preliminar del cuadro de diálogo Opciones de Visual Studio":::

#### <a name="commit-details"></a>Detalles de la confirmación

Al hacer doble clic en una **Confirmación** , Visual Studio abre los detalles en una ventana de herramientas independiente. Aquí puede revertir la confirmación, restablecer la confirmación, modificar el mensaje de confirmación o crear una etiqueta en la confirmación. Al hacer clic en un archivo cambiado en la confirmación, Visual Studio abre la vista en paralelo **Diferencias** de la confirmación y su elemento primario.

:::image type="content" source="media/git-branch-commit-details.png" alt-text="Captura de pantalla de la sección Características en versión preliminar del cuadro de diálogo Opciones de Visual Studio":::

## <a name="handle-merge-conflicts"></a>Control de conflictos de combinación

Pueden producirse conflictos durante una combinación si dos desarrolladores modifican las mismas líneas en un archivo y Git no sabe automáticamente cuál es la correcta. Git detiene la fusión mediante combinación e informa de que está en un estado Con conflictos.

Visual Studio hace que sea fácil identificar y resolver un conflicto de fusión mediante combinación. En primer lugar, la ventana **Repositorio de GIT** muestra una barra de información dorada en la parte superior de la ventana.

:::image type="content" source="media/git-merge-conflict-gold-bar.png" alt-text="Captura de pantalla de la sección Características en versión preliminar del cuadro de diálogo Opciones de Visual Studio" *Fusión mediante combinación en curso con conflictos* ", con los archivos sin combinar en su sección independiente debajo.

:::image type="content" source="media/git-merge-progress-conflicts-message.png" alt-text="Captura de pantalla de la sección Características en versión preliminar del cuadro de diálogo Opciones de Visual Studio":::

Pero si ninguna de estas ventanas se abre y, en su lugar, se va al archivo que tiene conflictos de combinación, no tendrá que buscar el texto siguiente:

```bash
    <<<<<<< HEAD
    =======
    >>>>>>> main
```

En su lugar, Visual Studio muestra una barra de información dorada en la parte superior de la página que indica que el archivo abierto tiene conflictos. A continuación, puede hacer clic en el vínculo para abrir el **editor de combinación** .

:::image type="content" source="media/git-merge-conflict-gold-info-bar.png" alt-text="Captura de pantalla de la sección Características en versión preliminar del cuadro de diálogo Opciones de Visual Studio":::

### <a name="the-merge-editor"></a>El editor de combinación

El editor de combinación de Visual Studio es una herramienta de combinación tridireccional que muestra los cambios entrantes, los cambios actuales y el resultado de la combinación. Puede usar la barra de herramientas situada en el nivel superior del **editor de combinación** para desplazarse entre los conflictos y las diferencias de combinación automática en el archivo.

:::image type="content" source="media/git-merge-editor.png" alt-text="Captura de pantalla de la sección Características en versión preliminar del cuadro de diálogo Opciones de Visual Studio":::

También puede usar los controles de alternancia para mostrar u ocultar las diferencias, mostrar u ocultar las diferencias de palabras y personalizar el diseño. Hay casillas en la parte superior de cada lado que puede usar para realizar todos los cambios de un lado o del otro. No obstante, para realizar cambios individuales, puede hacer clic en las casillas situadas a la izquierda de las líneas en conflicto en cualquier lado. Por último, cuando termine de resolver los conflictos, puede seleccionar el botón **Aceptar combinación** del editor de combinación. Escriba luego un mensaje de confirmación y confirme los cambios para completar la resolución.

## <a name="personalize-your-git-settings"></a>Personalización de la configuración de Git

Para personalizar la configuración de Git en un nivel de repositorio, así como en un nivel global, vaya a **Git** > **Configuración** o a **Herramientas** > **Opciones** > **Control de código fuente** en la barra de menús. Después, elija las opciones que quiera.

:::image type="content" source="media/git-options-settings.png" alt-text="Captura de pantalla de la sección Características en versión preliminar del cuadro de diálogo Opciones de Visual Studio":::

## <a name="whats-next"></a>Pasos siguientes

Manténgase atento: esta página se actualizará a medida que se siga perfeccionando la nueva experiencia de Git en Visual Studio 2019.

> [!IMPORTANT]
> Si tiene alguna sugerencia para nosotros, háganoslo saber. Agradecemos la oportunidad de participar en sus decisiones de diseño a través del portal [**Developer Community**](https://aka.ms/vs-suggest).

## <a name="see-also"></a>Consulte también

- Vídeo sobre [la nueva experiencia de Git](https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/The-New-Git-Experience) en Channel 9 y [YouTube](https://www.youtube.com/watch?v=ZiQ2LXtAJ6I&feature=youtu.be)
- Entrada de blog [Nuevas y emocionantes actualizaciones relativas a la experiencia de Git en Visual Studio](https://devblogs.microsoft.com/visualstudio/exciting-new-updates-to-the-git-experience-in-visual-studio/)
- Entrada de blog [Experiencia mejorada de Git en Visual Studio 2019](https://devblogs.microsoft.com/visualstudio/improved-git-experience-in-visual-studio-2019/)
- [Notas de la versión de Visual Studio 2019](/visualstudio/releases/2019/release-notes)
