---
title: Компилятора (уровень 4) предупреждение C4457 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4457
dev_langs:
- C++
helpviewer_keywords:
- C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80eac0ade54df1626e993bfed12468b2aa34402f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4457"></a>Компилятора (уровень 4) предупреждение C4457
  
> объявление "*идентификатор*" скрывает параметр функции
  
Объявление *идентификатор* в локальной области видимости скрывает объявление параметра функции с одинаковыми именами. Это предупреждение позволяет узнать, который ссылается на *идентификатор* в локальной области разрешения локально объявленных версию, а не параметр, который может быть или не быть поставленной цели. Чтобы устранить эту проблему, рекомендуется дать имена локальных переменных, которые не конфликтуют с именами параметров.  
    
## <a name="example"></a>Пример
  
Следующий пример приводит к возникновению ошибки C4457 из-за параметра `x` , а локальную переменную `x` в `member_fn` с теми же именами. Чтобы устранить эту проблему, используйте разные имена для параметров и локальных переменных.  
  
```cpp  
// C4457_hide.cpp
// compile with: cl /W4 /c C4457_hide.cpp

struct S {
    void member_fn(unsigned x) {
        double a = 0;
        for (int x = 0; x < 10; ++x) {  // C4457
            a += x; // uses local x
        } 
        a += x; // uses parameter x
    }
} s;
```  
