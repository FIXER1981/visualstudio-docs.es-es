---
title: CV_call_e | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CV_call_e enumeration
ms.assetid: f230560b-4243-432d-8f19-46df112043b9
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: cd1ee4c024894e5752277a5000d37745c88c4ac6
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "63442108"
---
# <a name="cvcalle"></a>CV_call_e
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Especifica la convención de llamada para una función.  
  
> [!NOTE]
> Solo los valores de enumeración más comunes se documentan aquí. La enumeración completa está disponible en el archivo de encabezado cvconst.h.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
typedef enum CV_call_e {   
   CV_CALL_NEAR_C    = 0x00,  
   CV_CALL_NEAR_FAST = 0x04,  
   CV_CALL_NEAR_STD  = 0x07,  
   CV_CALL_NEAR_SYS  = 0x09,  
   CV_CALL_THISCALL  = 0x0b,  
   CV_CALL_CLRCALL   = 0x16  
} CV_call_e;  
```  
  
## <a name="elements"></a>Elementos  
 CV_CALL_NEAR_C  
 Especifica una convención de llamada a función mediante una inserción casi de derecha a izquierda. La función llamada borra la pila.  
  
 CV_CALL_NEAR_FAST  
 Especifica una convención de llamada a función mediante una inserción de izquierda a derecha casi con registros. La función llamada utiliza la suma de bytes de parámetro para borrar la pila.  
  
 CV_CALL_NEAR_STD  
 Especifica una convención de llamada a función mediante una llamada estándar casi (inserción de derecha a izquierda).  
  
 CV_CALL_NEAR_SYS  
 Especifica una convención de llamada a función mediante una llamada del sistema casi.  
  
 CV_CALL_THISCALL  
 Especifica una convención de llamada a función utilizando `this` llamar (`this` puntero pasa en el registro).  
  
 CV_CALL_CLRCALL  
 Especifica una convención de llamada de función utilizada por el Common Language Runtime (CLR) (también conocido como un código administrado convención de llamada).  
  
## <a name="remarks"></a>Comentarios  
 Los valores de esta enumeración se devuelven mediante una llamada a la [Get_callingconvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md) método.  
  
## <a name="requirements"></a>Requisitos  
 Encabezado: cvconst.h  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones y estructuras](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_callingConvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)
