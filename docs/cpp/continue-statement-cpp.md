---
title: "Оператор Continue (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- continue_cpp
dev_langs:
- C++
helpviewer_keywords:
- continue keyword [C++]
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 502254adc8b01966182f911af5a0dce8af36c1f3
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="continue-statement-c"></a>Оператор continue (C++)
Принудительно вызывает передачу управления управляющему выражению наименьшего внешнего [сделать](../cpp/do-while-statement-cpp.md), [для](../cpp/for-statement-cpp.md), или [при](../cpp/while-statement-cpp.md) цикла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
continue;  
```  
  
## <a name="remarks"></a>Примечания  
 Все остальные операторы текущей итерации не выполняются. Следующая итерация цикла определяется следующим образом.  
  
-   В цикле `do` или `while` следующая итерация начинается путем повторного вычисления управляющего выражения оператора `do` или `while`.  
  
-   В цикле `for` (в котором используется синтаксис `for`(`init-expr`; `cond-expr`; `loop-expr`)) выполняется предложение `loop-expr`. Затем повторно выполняется предложение `cond-expr` и, в зависимости от результата, цикл завершается или начинается другая итерация.  
  
 В следующем примере показано использование оператора `continue` для обхода фрагментов кода и начала выполнения следующей итерации цикла.  
  
## <a name="example"></a>Пример  
  
```  
// continue_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        i++;  
        printf_s("before the continue\n");  
        continue;  
        printf("after the continue, should never print\n");  
     } while (i < 3);  
  
     printf_s("after the do loop\n");  
}  
```  
  
```Output  
before the continue  
before the continue  
before the continue  
after the do loop  
```  
  
## <a name="see-also"></a>См. также  
 [Операторы перехода](../cpp/jump-statements-cpp.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)
