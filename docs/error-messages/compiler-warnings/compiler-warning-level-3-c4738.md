---
title: "Предупреждение (уровень 3) C4738 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4738
dev_langs:
- C++
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: ce2db890b7b90eedf5b4456e875a06f8f92b0289
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="compiler-warning-level-3-c4738"></a>Предупреждение компилятора (уровень 3) C4738
хранение результатов в памяти в 32-разрядном формате с плавающей запятой, возможно снижение производительности  
  
 C4738 предупреждает о том, что результат присваивания, приведения, передачи аргумента или другой операции может потребоваться округлить, или, что операция не хватило регистров и требуется для использования памяти. Это может привести к потере производительности.  
  
 Чтобы устранить это предупреждение и избежать округления, компиляция с [/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md) или использовать `double` вместо `float`.  
  
 Чтобы устранить это предупреждение и предотвращения нехватки регистров, изменить порядок вычисления и изменить применение встраивание  
  
 Это предупреждение отключено по умолчанию. Дополнительные сведения см. в разделе [компилятора предупреждения выключенные по умолчанию](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4738:  
  
```  
// C4738.cpp  
// compile with: /c /fp:precise /O2 /W3  
// processor: x86  
#include <stdio.h>  
  
#pragma warning(default : 4738)  
  
float func(float f)  
{  
    return f;  
}  
  
int main()  
{  
    extern float f, f1, f2;  
    double d = 0.0;  
  
    f1 = func(d);  
    f2 = (float) d;  
    f = f1 + f2;   // C4738  
    printf_s("%f\n", f);  
}  
```
