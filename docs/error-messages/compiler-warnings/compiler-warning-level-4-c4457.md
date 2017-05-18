---
title: "Компилятора (уровень 4) предупреждение C4457 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4457
dev_langs:
- C++
helpviewer_keywords:
- C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
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
ms.openlocfilehash: 4977ade625e3f4af5f01364b865d2c2f41ebe80a
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017

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

