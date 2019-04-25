---
title: Procedimiento Usar elementos coloreables integrados | Documentos de Microsoft
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- colorable items
- language services, built-in colorable items
ms.assetid: 5e5f3436-6bad-4fd2-8823-6a30353ba648
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e82b28a22d64ed1a97e2f932368da266b6b79d56
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56603058"
---
# <a name="how-to-use-built-in-colorable-items"></a>Filtrar Usar elementos coloreables integrados
Antes de usar los elementos coloreables integrados, debe en primer lugar señalar al entorno de desarrollo integrado (IDE) que no proporcionan sus propios elementos coloreables personalizados, que en este caso sería <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> objetos. Para ello, establezca una entrada del registro del servicio de lenguaje.

## <a name="to-use-built-in-colorable-items"></a>Para usar elementos coloreables integrados

1. En **HKEY_LOCAL_MACHINE\VisualStudio\\< X.Y > \Languages\Language Services\\< Nombreidioma\>**, donde \<X.Y > es una versión de [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] y \<Nombreidioma > es el nombre de su lenguaje, cree un valor de entrada del Registro DWORD llamado **RequestStockColors**.

2. Establecer el **RequestStockColors** valores de entrada del registro para *1*.

    Después de crear la entrada del registro, el Coloreador <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> método puede utilizar los miembros de la <xref:Microsoft.VisualStudio.TextManager.Interop.DEFAULTITEMS> enumeración para rellenar la matriz de atributos de color para su uso por el editor.

   > [!NOTE]
   >  No establezca esta entrada del registro si va a proporcionar elementos coloreables personalizados. Para obtener más información, consulte [elementos coloreables personalizados](../../extensibility/internals/custom-colorable-items.md).

## <a name="see-also"></a>Vea también
- [Colores de sintaxis en editores personalizados](../../extensibility/syntax-coloring-in-custom-editors.md)
- [Colores de sintaxis en un servicio de lenguaje heredado](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)
- [Implementación de colores de sintaxis](../../extensibility/internals/implementing-syntax-coloring.md)
- [Elementos coloreables personalizados](../../extensibility/internals/custom-colorable-items.md)
- [Registrar un servicio de lenguaje heredado](../../extensibility/internals/registering-a-legacy-language-service2.md)