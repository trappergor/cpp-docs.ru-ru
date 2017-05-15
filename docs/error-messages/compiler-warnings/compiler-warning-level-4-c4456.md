---
title: "Предупреждение (уровень 4) C4456 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4456
dev_langs:
- C++
helpviewer_keywords:
- C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
caps.latest.revision: 0
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
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 8698c9a430a79bbec1f6e82b8ac58067317c59a1
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017

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

