---
title: Comando Ir a | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- edit.goto
helpviewer_keywords:
- Debug.Goto command
- Go To command
ms.assetid: 201e1dd2-6701-467d-8cc1-faec2ef20511
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 010d2c395d77be590b3d8d3bc26fc83aaa63adfa
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2019
ms.locfileid: "59660611"
---
# <a name="go-to-command"></a>Ir a (Comando)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Mueve el cursor a la línea especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Edit.GoTo [linenumber]  
```  
  
## <a name="arguments"></a>Argumentos  
 `linenumber`  
 Opcional. Entero que representa el número de la línea a la que se debe ir.  
  
## <a name="remarks"></a>Comentarios  
 La numeración de líneas empieza por el uno. Si el valor de `linenumber` es menor que uno, se muestra la primera línea. Si el valor de `linenumber` es mayor que el número de la última línea, se muestra la última línea.  
  
 Si no se especifica ningún valor para `linenumber`, se muestra el cuadro de diálogo **Ir a la línea**.  
  
 El alias de este comando es GoToLn.  
  
## <a name="example"></a>Ejemplo  
  
```  
>Edit.GoTo 125  
```  
  
## <a name="see-also"></a>Vea también  
 [Comandos de Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Ventana Comandos](../../ide/reference/command-window.md)   
 [Cuadro Buscar/Comando](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)
