---
title: Procedimiento Crear y modificar propiedades de documento personalizadas
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom document properties
- documents [Office development in Visual Studio], properties
- document properties [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: aefe931bf4b53f0637c4bac1216e313b7a6fb092
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57526508"
---
# <a name="how-to-create-and-modify-custom-document-properties"></a>Filtrar Crear y modificar propiedades de documento personalizadas
  Las aplicaciones de Microsoft Office enumeradas anteriormente proporcionan propiedades integradas que se almacenan con los documentos. Además, puede crear y modificar propiedades de documento personalizadas si hay información adicional que desea almacenar con el documento.

 [!INCLUDE[appliesto_docprops](../vsto/includes/appliesto-docprops-md.md)]

 Use la propiedad CustomDocumentProperties de un documento para trabajar con propiedades personalizadas. Por ejemplo, en un proyecto de nivel de documento para Microsoft Office Excel, use la propiedad <xref:Microsoft.Office.Tools.Excel.Workbook.CustomDocumentProperties%2A> de la clase `ThisWorkbook` . En un proyecto de complemento de VSTO para Excel, use la propiedad <xref:Microsoft.Office.Interop.Excel._Workbook.CustomDocumentProperties%2A> de un objeto <xref:Microsoft.Office.Interop.Excel.Workbook> . Estas propiedades devuelven un objeto <xref:Microsoft.Office.Core.DocumentProperties> , que es una colección de objetos <xref:Microsoft.Office.Core.DocumentProperty> . Puede usar la propiedad `Item` de la colección para recuperar una propiedad determinada, ya sea por nombre o por índice dentro de la colección.

 En el ejemplo siguiente se muestra cómo agregar una propiedad personalizada en una personalización de nivel de documento para Excel y asignarle un valor.

 ## <a name="example"></a>Ejemplo
 [!code-vb[Trin_VstcoreProgramming#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/ThisWorkbook.vb#6)]
 [!code-csharp[Trin_VstcoreProgramming#6](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingExcelCS/ThisWorkbook.cs#6)]

## <a name="robust-programming"></a>Programación sólida
 Si se intenta acceder a la propiedad `Value` para propiedades sin definir, se produce una excepción.

## <a name="see-also"></a>Vea también
- [Programar complementos VSTO](../vsto/programming-vsto-add-ins.md)
- [Programar personalizaciones de nivel de documento](../vsto/programming-document-level-customizations.md)
- [Cómo: Leer y escribir en las propiedades del documento](../vsto/how-to-read-from-and-write-to-document-properties.md)
