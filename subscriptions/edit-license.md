---
title: Edición de suscripciones en el Portal de administración | Microsoft Docs
author: evanwindom
ms.author: v-evwin
manager: cabuschl
ms.assetid: 97ac8e4d-7a03-42f8-98cb-15bcaa90ef65
ms.date: 09/21/2020
ms.topic: how-to
description: Obtenga más información sobre cómo los administradores pueden editar asignaciones de suscripción.
ms.openlocfilehash: 060ae7c7679eb1bf9dc4da99ea9a1bf952ebc58b
ms.sourcegitcommit: 4affcf2830337e6aba84621c3eda5faf5d0d4a01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91022565"
---
# <a name="edit-visual-studio-subscription-assignments"></a>Edición de asignaciones de suscripciones de Visual Studio
Como administrador de suscripciones, puede hacer cambios en las suscripciones asignadas a personas de su organización.  En este artículo se describen los tipos de cambios que puede realizar y se proporcionan los pasos necesarios.

   > [!NOTE]
   > Si necesita cambiar los detalles de la suscripción de un suscriptor asignado a través de un grupo de Azure Active Directory, deberá quitarlos del grupo y agregarlos al portal de administración individualmente.  

## <a name="change-subscriber-information"></a>Cambio de la información del suscriptor
Puede editar la información del suscriptor para corregir los errores o actualizarla.

Para editar un suscriptor, seleccione los puntos suspensivos (...) que aparecen junto a la dirección de correo electrónico del suscriptor al mantener el mouse sobre él. Aparecerá una lista desplegable.  Seleccione **Editar** para modificar los detalles del suscriptor. 
> [!div class="mx-imgBorder"]
> ![Selección de un suscriptor para editarlo](_img/edit-license/select-subscriber.png "Haga clic en el botón de puntos suspensivos y elija Editar.")

Puede actualizar el nombre del suscriptor, el apellido, el nivel de suscripción, la dirección de correo electrónico, el país o región, el idioma, las descargas y el campo de referencia. Edite la información del suscriptor y haga clic en **Guardar**.

## <a name="edit-multiple-subscribers-using-bulk-edit"></a>Edición en masa de varios suscriptores


Puede editar varios suscriptores a la vez mediante el proceso de edición en masa. Esta característica se usa principalmente en organizaciones que están efectuando cambios en la dirección de correo electrónico corporativa o cuando una organización ha decidido restringir el acceso a las descargas.

Vea este vídeo o siga leyendo saber cómo editar varios suscriptores mediante la edición en masa. 
<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vkAF]

   > [!IMPORTANT]
   > Los niveles de suscripción, es decir, Enterprise, Professional, etc., y los GUID de suscripción no se pueden modificar con la edición masiva.  Si necesita asignar GUID de suscripción específicos a los usuarios, use el proceso para agregar usuarios eligiendo el identificador de suscripción. Si intenta realizar una carga con estos elementos cambiados en la plantilla de edición masiva, no podrá hacerla.

1. Para editar varios suscriptores a la vez, navegue hasta la pestaña Suscriptores. En la cinta de la parte superior, haga clic en **Edición en masa**.

2. La edición en masa usa una plantilla de Excel para realizar modificaciones en la información de los suscriptores. En el cuadro Edición en masa, haga clic en **Export this Excel** (Exportar este Excel) para descargar la lista actual de los suscriptores con toda su información.
   > [!div class="mx-imgBorder"]
   > ![Edición de una licencia: exportación en masa de la lista de ediciones](_img/edit-license/edit-license-bulk-edit-export.png "Haga clic en Exportar este Excel para crear una lista de sus suscripciones actuales.")

3. Después, guarde el archivo localmente de modo que pueda encontrarlo fácilmente y realizar los cambios necesarios antes de cargarlo. Para garantizar una carga correcta, **no edite el nivel de suscripción ni el GUID de suscripción** en el archivo de edición masiva, ya que si lo hace la carga no se podrá efectuar.

4. Vuelva al Portal de administradores de suscripciones de Visual Studio y, en el cuadro de diálogo Edición en masa, haga clic en **Examinar**. Seleccione el archivo de Excel que ha guardado y haga clic en **Aceptar**. Verá el progreso de la carga en la pantalla.
   > [!div class="mx-imgBorder"]
   > ![Edición de una licencia: carga de archivos de ediciones en masa](_img/edit-license/edit-license-bulk-file-upload1.png "Vaya a la ubicación del archivo de Excel completado, selecciónelo y haga clic en Aceptar.")

5. Cuando haya cargado el archivo, verá una notificación en la que se le indicará que se ha realizado correctamente. En este momento, los cambios se reflejarán en la información del suscriptor.

## <a name="see-also"></a>Vea también
- [Documentación de Visual Studio](/visualstudio/)
- [Documentación de Azure DevOps](/azure/devops/)
- [Documentación de Azure](/azure/)
- [Documentación de Microsoft 365](/microsoft-365/)

## <a name="next-steps"></a>Pasos siguientes
- ¿Necesita asignar un identificador de suscripción específico? Consulte la asignación de un identificador de suscripción. 
- Si necesita ayuda para encontrar una suscripción determinada, consulte [Búsqueda de suscripciones](search-license.md).
- ¿Necesita crear una lista de todas las suscripciones?  Consulte [Exportar suscripciones](exporting-subscriptions.md).