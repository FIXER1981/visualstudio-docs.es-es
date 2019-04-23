---
title: Desactivar restricciones al llenar un conjunto de datos
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- DataRow.BeginEdit
- DataRow.EndEdit
- DataRow.CancelEdit
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- updating datasets, constraints
- constraints [Visual Basic], datasets
- datasets [Visual Basic], constraints
- constraints [Visual Basic], suspending during dataset update
ms.assetid: 553f7d0c-2faa-4c17-b226-dd02855bf1dc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 9aca29de7e9c5a01e0c2caad2c42015cd31b3f75
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "60102866"
---
# <a name="turn-off-constraints-while-filling-a-dataset"></a>Desactivar restricciones al llenar un conjunto de datos

Si un conjunto de datos contiene restricciones (como las restricciones de clave externa), pueden producir errores relacionados con el orden de las operaciones que se realizan en el conjunto de datos. Por ejemplo, cargar registros secundarios antes de la carga relacionadas registros primarios pueden infringir una restricción y producir un error. Tan pronto como se carga un registro secundario, la restricción comprueba el registro principal existente y produce un error.

Si no hubiera ningún mecanismo para permitir la suspensión temporal de la restricción, se produciría un error cada vez que se intentara cargar un registro en la tabla secundaria. Otra manera de suspender todas las restricciones de un conjunto de datos es mediante las propiedades <xref:System.Data.DataRow.BeginEdit%2A> y <xref:System.Data.DataRow.EndEdit%2A>.

> [!NOTE]
> Eventos de validación (por ejemplo, <xref:System.Data.DataTable.ColumnChanging> y <xref:System.Data.DataTable.RowChanging>) no se genera cuando las restricciones están desactivadas.

## <a name="to-suspend-update-constraints-programmatically"></a>Para suspender las restricciones de actualización mediante programación

- En el ejemplo siguiente se muestra cómo desactivar temporalmente la comprobación de restricciones de un conjunto de datos:

     [!code-csharp[VbRaddataEditing#10](../data-tools/codesnippet/CSharp/turn-off-constraints-while-filling-a-dataset_1.cs)]
     [!code-vb[VbRaddataEditing#10](../data-tools/codesnippet/VisualBasic/turn-off-constraints-while-filling-a-dataset_1.vb)]

## <a name="to-suspend-update-constraints-using-the-dataset-designer"></a>Para suspender las restricciones de actualización mediante el Diseñador de DataSet

1. Abra su conjunto de datos en el **Diseñador de Dataset**. Para obtener más información, vea [Tutorial: Creación de un conjunto de datos en el Diseñador de Dataset](walkthrough-creating-a-dataset-with-the-dataset-designer.md).

2. En la ventana **Propiedades** , establezca la propiedad <xref:System.Data.DataSet.EnforceConstraints%2A> en `false`.

## <a name="see-also"></a>Vea también

- [Llenar conjuntos de datos mediante TableAdapters](../data-tools/fill-datasets-by-using-tableadapters.md)
- [Relaciones en conjuntos de datos](../data-tools/relationships-in-datasets.md)