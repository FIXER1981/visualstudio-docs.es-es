---
title: Protección mediante contraseña en documentos de Office
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- permissions [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- passwords [Office development in Visual Studio], document protections
- documents [Office development in Visual Studio], restricted permissions
- Office documents [Office development in Visual Studio, restricted permissions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e3c9521389ce348a482f35ec95c9766edea49f5f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "62977905"
---
# <a name="password-protection-on-office-documents"></a>Protección mediante contraseña en documentos de Office
  Es posible establecer una contraseña en el Microsoft Office documentos de Word y Microsoft Office libros de Excel para que no se puedan abrir por alguien que no conozca la contraseña. Esta opción se denomina **contraseña al abrirse**.

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

 Puede crear proyectos de nivel de documento con documentos y libros existentes que tengan habilitada la opción **contraseña al abrir** . El comportamiento de Visual Studio es diferente para los documentos de Word y Excel que tienen habilitada la opción **contraseña al abrir** .

 Para obtener información sobre cómo habilitar la **contraseña al abrir**, vea la ayuda de en Word o Excel.

## <a name="behavior-of-excel-and-word"></a>Comportamiento de Excel y Word
 Cada vez que abre un libro de Excel en Visual Studio que tiene habilitada la opción Habilitar **contraseña en abierto** , Excel le solicitará la contraseña. Al compilar la solución, se le solicitará la contraseña de nuevo, ya que el documento se abre durante la compilación.

 La primera vez que abra un documento de Word en Visual Studio que tenga habilitada la opción **contraseña en abrir** , Word le pedirá la contraseña. Después de escribir correctamente la contraseña, la **contraseña al abrir** se quita del documento y al abrir el documento ya no se necesitará una contraseña. Si desea que el documento de la solución requiera una contraseña antes de que se pueda abrir, debe habilitar la **contraseña al abrirla** después de la compilación final y antes de implementar la solución.

## <a name="see-also"></a>Consulte también
- [Protección de documentos en soluciones de nivel de documento](../vsto/document-protection-in-document-level-solutions.md)
- [Información general sobre Information Rights Management y extensiones de código administrado](../vsto/information-rights-management-and-managed-code-extensions-overview.md)
- [Cómo: permitir que el código se ejecute en documentos con permisos restringidos](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)
- [Diseñar y crear soluciones de Office](../vsto/designing-and-creating-office-solutions.md)
