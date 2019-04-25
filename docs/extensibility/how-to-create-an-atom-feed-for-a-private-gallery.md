---
title: Filtrar Crear un átomo fuentes de distribución para una galería privada | Documentos de Microsoft
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Atom feed, VSIX private galleries
- VSIX private galleries, Atom feed
ms.assetid: 5897f538-9c41-486f-97d9-a1976d20d9fd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 094bff5c761a45e936f14f79587b4846d3838610
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56722413"
---
# <a name="how-to-create-an-atom-feed-for-a-private-gallery"></a>Procedimiento Crear una fuente Atom para una galería privada
Puede crear un átomo (RSS) de la fuente en una ubicación de la intranet que contiene las extensiones y agrega la fuente a **extensiones y actualizaciones** como una galería privada. Para obtener más información, consulte [galerías privadas](../extensibility/private-galleries.md).

## <a name="create-an-atom-feed"></a>Crear una fuente Atom
 Para crear una fuente como una galería privada Atom, primero recopilar sus extensiones (*.vsix* archivos) en una carpeta. Si desea que se puede organizarlos en subcarpetas. También necesitará los siguientes recursos:

- Un *atom.xml* archivo que pone a disposición las extensiones como galería privada. Para obtener información sobre cómo conectar el *atom.xml* archivo **extensiones y actualizaciones**, consulte [galerías privadas](../extensibility/private-galleries.md).

- Una carpeta que contiene los archivos de imagen que se han extraído de las extensiones (por ejemplo, capturas de pantalla). El *atom.xml* archivo contiene vínculos relativos a estas imágenes para que estén disponibles en **extensiones y actualizaciones**.

  Por ejemplo, suponga que haya recopilado las siguientes dos extensiones en una carpeta:

- *Template_Wizard_239.vsix*, que es una plantilla de proyecto VSIX vacía.

- *SelectionHighlight.vsix*, que es una herramienta para resaltar todas las instancias de una palabra seleccionada.

  El contenido de la *atom.xml* archivo podría parecerse al siguiente ejemplo:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<feed xmlns="http://www.w3.org/2005/Atom">
  <title type="text" />
  <id>uuid:bcecded5-97c8-4d24-96f1-7d9e16652433;id=1</id>
  <updated>2011-04-14T21:25:48Z</updated>
  <entry>
    <id>SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa</id>
    <title type="text">Highlight all occurrences of selected word</title>
    <summary type="text">This extends the editor to highlight ....</summary>
    <published>2011-04-14T14:24:51-07:00</published>
    <updated>2011-04-14T14:24:22-07:00</updated>
    <author>
      <name>Microsoft</name>
    </author>
    <link rel="icon" href="VSIXImages/SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa_Icon_SelectionHighlightIcon.jpg" />
    <link rel="previewimage" href="VSIXImages/SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa_PreviewImage_SelectionHighlight.jpg" />
    <content type="application/octet-stream" src="SelectionHighlight.vsix" />
    <Vsix xmlns="http://schemas.microsoft.com/developer/vsx-syndication-schema/2010" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <Id>SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa</Id>
      <Version>1.31</Version>
      <References />
      <Rating xsi:nil="true" />
      <RatingCount xsi:nil="true" />
      <DownloadCount xsi:nil="true" />
    </Vsix>
  </entry>
  <entry>
    <id>Template_Wizard_239.Microsoft.3b38a7e3-5cbc-4389-a92a-d82tyc2ed592</id>
    ...
  </entry>
</feed>
```

 Tenga en cuenta que las etiquetas de dos vínculo hacen referencia a las capturas de pantalla en la carpeta de imágenes generada.

## <a name="see-also"></a>Vea también
- [Galerías privadas](../extensibility/private-galleries.md)
