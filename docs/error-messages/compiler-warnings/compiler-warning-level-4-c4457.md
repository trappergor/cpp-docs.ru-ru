---
title: "Компилятора (уровень 4) предупреждение C4457 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4457
dev_langs: C++
helpviewer_keywords: C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
caps.latest.revision: "0"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 77965ba08b311768b54788692d3f5b7fa724f5b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
