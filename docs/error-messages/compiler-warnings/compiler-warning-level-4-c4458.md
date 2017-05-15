---
title: "Предупреждение (уровень 4) C4458 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4458
dev_langs:
- C++
helpviewer_keywords:
- C4458
ms.assetid: 7bdaa1b1-0caf-4d68-98c4-6bdd441c23fb
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
ms.openlocfilehash: 07b8db673b2db27f456f0e7228695c83497d1278
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-4-c4458"></a>Компилятор C4458 предупреждение (уровень 4)
  
> объявление "*идентификатор*" скрывает член класса
  
Объявление *идентификатор* в локальной области видимости скрывает объявление с идентичными именами *идентификатор* в области класса. Это предупреждение позволяет узнать, который ссылается на *идентификатор* в этой области разрешается локально объявленных версии, а не класс член версию, что может быть или не быть намерениям. Чтобы устранить эту проблему, рекомендуется дать имена локальных переменных, которые не конфликтуют с имена членов класса.  
    
## <a name="example"></a>Пример
  
Следующий пример приводит к возникновению ошибки C4458 из-за параметра `x` , а локальную переменную `y` в `member_fn` имеют те же имена, как данные-член класса. Чтобы устранить эту проблему, используйте разные имена для параметров и локальных переменных.  
  
```cpp  
// C4458_hide.cpp
// compile with: cl /W4 /c C4458_hide.cpp

struct S {
    int x;
    float y;
    void member_fn(long x) {   // C4458
        double y;  // C4458
        y = x;  
        // To fix this issue, change the parameter name x
        // and local name y to something that does not 
        // conflict with the data member names.
    }
} s;
```  

