---
title: "Предупреждение (уровень 4) C4458 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4458
dev_langs: C++
helpviewer_keywords: C4458
ms.assetid: 7bdaa1b1-0caf-4d68-98c4-6bdd441c23fb
caps.latest.revision: "0"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5dc5e3e49a8581fda9ecf83df2a96056bec38d7b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
