---
title: Procedimiento para guardar datos mediante una transacción
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- saving data, using transactions
- System.Transactions namespace
- transactions, saving data
- data [Visual Studio], saving
ms.assetid: 8b835e8f-34a3-413d-9bb5-ebaeb87f1198
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 40894adefb42d6de077a2e2812d26f90bc5f40dd
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "85281700"
---
# <a name="how-to-save-data-by-using-a-transaction"></a>Procedimiento para guardar datos mediante una transacción

Los datos se guardan en una transacción mediante el <xref:System.Transactions> espacio de nombres. Utilice el <xref:System.Transactions.TransactionScope> objeto para participar en una transacción que se administra automáticamente.

Los proyectos no se crean con una referencia al ensamblado *System. Transactions* , por lo que debe agregar manualmente una referencia a los proyectos que usan transacciones.

La forma más fácil de implementar una transacción es crear una instancia <xref:System.Transactions.TransactionScope> de un objeto en una `using` instrucción. (Para obtener más información, vea uso de la [instrucción](/dotnet/visual-basic/language-reference/statements/using-statement)y la [instrucción using](/dotnet/csharp/language-reference/keywords/using-statement)). El código que se ejecuta dentro de la `using` instrucción participa en la transacción.

Para confirmar la transacción, llame al <xref:System.Transactions.TransactionScope.Complete%2A> método como la última instrucción del bloque using.

Para revertir la transacción, inicie una excepción antes de llamar al <xref:System.Transactions.TransactionScope.Complete%2A> método.

## <a name="to-add-a-reference-to-the-systemtransactionsdll"></a>Para agregar una referencia al System.Transactions.dll

1. En el menú **Proyecto**, seleccione **Agregar referencia**.

2. En la pestaña **.net** (pestaña**SQL Server** para proyectos de SQL Server), seleccione **System. Transactions**y, después, haga clic en **Aceptar**.

     Se agrega al proyecto una referencia a *System.Transactions.dll* .

## <a name="to-save-data-in-a-transaction"></a>Para guardar datos en una transacción

- Agregue código para guardar los datos en la instrucción using que contiene la transacción. En el código siguiente se muestra cómo crear y crear instancias <xref:System.Transactions.TransactionScope> de un objeto en una instrucción using:

     [!code-vb[VbRaddataSaving#11](../data-tools/codesnippet/VisualBasic/save-data-by-using-a-transaction_1.vb)]
     [!code-csharp[VbRaddataSaving#11](../data-tools/codesnippet/CSharp/save-data-by-using-a-transaction_1.cs)]

## <a name="see-also"></a>Consulte también

- [Guardar los datos de nuevo en la base de datos](../data-tools/save-data-back-to-the-database.md)
- [Tutorial: Guardar datos en una transacción](../data-tools/save-data-in-a-transaction.md)
