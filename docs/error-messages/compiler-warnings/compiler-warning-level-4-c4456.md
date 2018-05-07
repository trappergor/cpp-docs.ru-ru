---
title: Предупреждение (уровень 4) C4456 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4456
dev_langs:
- C++
helpviewer_keywords:
- C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ca4af4e7353595dc687b77fa87acf70861bcb6f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4456"></a>Компилятор C4456 предупреждение (уровень 4)
  
> объявление "*идентификатор*" скрывает предыдущее локальное объявление
  
Объявление *идентификатор* в локальной области видимости скрывает объявление предыдущее локальное объявление с тем же именем. Это предупреждение позволяет узнать, который ссылается на *идентификатор* в локальной области разрешения локально объявленных версии не предыдущих local, что может не соответствовать намерениям. Чтобы устранить эту проблему, рекомендуется дать имена локальных переменных, которые не конфликтуют с других локальных имен.  
    
## <a name="example"></a>Пример
  
Следующий пример приводит к возникновению ошибки C4456, так как переменная управления цикла `int x` , а локальную переменную `double x` в `member_fn` с теми же именами. Чтобы устранить эту проблему, используйте разные имена локальных переменных.  
  
```cpp  
// C4456_hide.cpp
// compile with: cl /W4 /c C4456_hide.cpp

struct S {
    void member_fn(unsigned u) {
        double x = 0;
        for (int x = 0; x < 10; ++x) {  // C4456
            u += x; // uses local int x
        } 
        x += u; // uses local double x
    }
} s;
```  
