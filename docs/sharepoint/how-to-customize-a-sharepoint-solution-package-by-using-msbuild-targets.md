---
title: Personalizar el paquete de soluciones de SharePoint mediante destinos de MSBuild
titleSuffix: ''
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packages
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 9845f755d184c18b6b5ade4c5504e393edae7b00
ms.sourcegitcommit: 9d2829dc30b6917e89762d602022915f1ca49089
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2020
ms.locfileid: "91585815"
---
# <a name="how-to-customize-a-sharepoint-solution-package-by-using-msbuild-targets"></a>Cómo: personalizar un paquete de solución de SharePoint mediante destinos de MSBuild
  Mediante el uso de destinos de MSBuild en un símbolo del sistema, puede personalizar el modo en que Visual Studio crea los archivos de paquete de SharePoint (*. wsp*). Por ejemplo, puede personalizar las propiedades de MSBuild para cambiar el directorio intermedio de empaquetado y los grupos de elementos de MSBuild que especifican los archivos enumerados.

## <a name="customize-and-run-msbuild-targets"></a>Personalizar y ejecutar destinos de MSBuild
 Si personaliza los destinos BeforeLayout y AfterLayout, puede realizar tareas antes del diseño del paquete, como agregar, quitar o modificar los archivos que se van a empaquetar.

#### <a name="to-customize-the-beforelayout-target"></a>Para personalizar el destino BeforeLayout

1. Abra un editor, como el Bloc de notas y, a continuación, agregue el código siguiente.

   ```xml
   <Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <Target Name="BeforeLayout">
       <Message Importance="high" Text="In the BeforeLayout Target"></Message>
     </Target>
   </Project>
   ```

    Este ejemplo muestra un mensaje antes del empaquetado de este destino.

2. Asigne al archivo el nombre **CustomLayout. SharePoint. targets**y guárdelo en la carpeta del proyecto de SharePoint.

3. Abra el proyecto, abra el menú contextual y, a continuación, elija **descargar el proyecto**.

4. En **Explorador de soluciones**, abra el menú contextual del proyecto y, a continuación, elija **Editar** * \<ProjectName> . vbproj* o **Editar** * \<ProjectName> . csproj*.

5. Después `Import` de la línea situada cerca del final del archivo de proyecto, agregue la línea siguiente.

   ```xml
   <Import Project="CustomLayout.SharePoint.targets" />
   ```

6. Guarda y cierra el archivo de proyecto.

7. En **Explorador de soluciones**, abra el menú contextual del proyecto y, a continuación, elija **volver a cargar el proyecto**.

   Al publicar el proyecto, el mensaje aparecerá en la salida antes de comenzar el empaquetado.

#### <a name="to-customize-the-afterlayout-target"></a>Para personalizar el destino AfterLayout

1. En la barra de menús, elija **archivo**  >  **abrir**  >  **archivo**.

2. En el cuadro de diálogo **Abrir archivo** , vaya a la carpeta del proyecto, elija el archivo CustomLayout. target y, a continuación, elija el botón **abrir** .

3. Justo antes de la `</Project>` etiqueta, agregue el código siguiente:

   ```xml
   <Target Name="AfterLayout">
     <Message Importance="high" Text="In the AfterLayout Target"></Message>
   </Target>
   ```

    En este ejemplo se muestra un mensaje después de empaquetar este destino.

4. Guarde y cierre el archivo de destinos.

5. Reinicie Visual Studio y, a continuación, abra el proyecto.

   Al publicar el proyecto, el mensaje BeforeLayout aparece antes de que se inicie el empaquetado y el mensaje AfterLayout aparece después de que finalice el empaquetado.

## <a name="see-also"></a>Vea también
- [Empaquetado e implementación de soluciones de SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)
