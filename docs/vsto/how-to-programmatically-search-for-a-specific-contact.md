---
title: Procedimiento Buscar un contacto específico mediante programación
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- contacts [Office development in Visual Studio], searching
- searching contacts
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: feff583d28bf53f4bffc9b425d52902688b80a4b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "63000325"
---
# <a name="how-to-programmatically-search-for-a-specific-contact"></a>Procedimiento Buscar un contacto específico mediante programación
  En este ejemplo se busca una carpeta de contactos de Outlook para un contacto específico por nombre y apellidos. En el ejemplo se supone que existe un contacto llamado **John Evans** en la carpeta Contactos.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>Ejemplo
 [!code-csharp[Trin_Outlook_RL_SearchForContact#1](../vsto/codesnippet/CSharp/trin_outlook_rl_searchforcontact/thisaddin.cs#1)]
 [!code-vb[Trin_Outlook_RL_SearchForContact#1](../vsto/codesnippet/VisualBasic/trin_outlook_rl_searchforcontact/thisaddin.vb#1)]

## <a name="see-also"></a>Vea también
- [Trabajar con elementos de contacto](../vsto/working-with-contact-items.md)
- [Empezar a programar complementos de VSTO](../vsto/getting-started-programming-vsto-add-ins.md)
