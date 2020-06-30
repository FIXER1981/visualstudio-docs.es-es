---
title: 'Cómo: agregar formas a un documento de Visio mediante programación'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visio [Office development in Visual Studio], adding Visio shapes
- shapes [Office development in Visual Studio], adding Visio shapes
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: adde20bff07b54a7fb5777bd9e03a995b4fbd7df
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2020
ms.locfileid: "85538065"
---
# <a name="how-to-programmatically-add-shapes-to-a-visio-document"></a>Cómo: agregar formas a un documento de Visio mediante programación
  Puede agregar formas a un documento de Microsoft Office Visio recuperando los patrones de una galería de símbolos y colocando las formas en la página activa.

 Para obtener más información, vea la documentación de referencia de VBA del método [Microsoft.Office.Interop.Visio.Documents.Add](/office/vba/api/Visio.Documents.Add) , la propiedad [Microsoft.Office.Interop.Visio.Application.ActivePage](/office/vba/api/Visio.Application.ActivePage) y el método [Microsoft.Office.Interop.Visio.Page.Drop](/office/vba/api/Visio.Page.Drop) .

## <a name="add-shapes-to-a-visio-document"></a>Agregar formas a un documento de Visio

### <a name="to-add-shapes-to-a-visio-document"></a>Para agregar formas a un documento de Visio

- Con un documento activo, recupere los patrones de la colección Documents.Masters y coloque las formas en el documento activo. Puede recuperar un patrón mediante el índice o el nombre del patrón.

     En el ejemplo de código siguiente se crea un documento de Visio en blanco y, a continuación, se abre con la galería de símbolos **Formas básicas** acoplada. A continuación, el código recupera varias formas y las coloca en la página activa.

     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#13)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#13)]

## <a name="see-also"></a>Consulte también
- [Soluciones de Visio](../vsto/visio-solutions.md)
- [Información general sobre el modelo de objetos de Visio](../vsto/visio-object-model-overview.md)
- [Trabajar con formas de Visio](../vsto/working-with-visio-shapes.md)
- [Cómo: copiar y pegar formas en un documento de Visio mediante programación](../vsto/how-to-programmatically-copy-and-paste-shapes-in-a-visio-document.md)
