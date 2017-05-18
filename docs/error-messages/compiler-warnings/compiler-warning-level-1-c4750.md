---
title: "Компилятор C4750 предупреждение (уровень 1) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4750
dev_langs:
- C++
helpviewer_keywords:
- C4750
ms.assetid: b0b2c938-7d2a-4c36-8270-7daee15ffee3
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 84f0628de933344eb23dc6325679abdcd3699c3a
ms.openlocfilehash: 6e22ef89b92a5b584979abbd370f82b482cf74e0
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4750"></a>Предупреждение компилятора (уровень 1) C4750
"идентификатор": функция с _alloca() включена в цикл  
  
 Функция «идентификатор» принудительно подстановку [_alloca](../../c-runtime-library/reference/alloca.md) функции в цикле, что может привести к переполнению стека, при выполнении цикла.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что функция «идентификатор» не будет изменен с [__forceinline](../../cpp/inline-functions-cpp.md) описатель.  
  
2.  Убедитесь, что функция «идентификатор» не содержит [_alloca](../../c-runtime-library/reference/alloca.md) функцию, которая содержится в цикле.  
  
3.  Не указывайте [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/ox](../../build/reference/ox-full-optimization.md), или [/Og](../../build/reference/og-global-optimizations.md) ключа компиляции.  
  
4.  Место [_alloca](../../c-runtime-library/reference/alloca.md) работать в [попробуйте-инструкции, за исключением](../../cpp/try-except-statement.md) который может перехватить переполнение стека.  
  
## <a name="example"></a>Пример  
 В следующем примере кода `MyFunction` вызывается в цикле, и `MyFunction` вызывает функцию `_alloca` . Модификатор `__forceinline` вызывает встраиваемую подстановку функции `_alloca` .  
  
```  
// c4750.cpp  
// compile with: /O2 /W1 /c  
#include <intrin.h>  
  
char * volatile newstr;  
  
__forceinline void myFunction(void) // C4750 warning  
{  
// The _alloca function does not require a __try/__except   
// block because the example uses compiler option /c.  
    newstr = (char * volatile) _alloca(1000);  
}  
  
int main(void)  
{  
    for (int i=0; i<50000; i++)  
       myFunction();  
    return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [_alloca](../../c-runtime-library/reference/alloca.md)
