---
title: "__restrict | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __restrict_cpp
dev_langs:
- C++
helpviewer_keywords:
- __restrict keyword [C++]
ms.assetid: 2d151b4d-f930-49df-bd16-d8757ec7fa83
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: c0ed875845323d4125a97ca004bb50385f59c53d
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="restrict"></a>__restrict
Как **__declspec ( [ограничить](../cpp/restrict.md) )** модификатора, `__restrict` ключевое слово указывает, что символ не является псевдонимом в текущей области. Ключевое слово `__restrict` отличается от модификатора `__declspec ( restrict )` следующим:  
  
-   Ключевое слово `__restrict` допустимо только в переменных, а `__declspec ( restrict )` — только в объявлениях и определениях функций.  
  
-   Ключевое слово `__restrict` похоже на ключевое слово `restrict` из спецификации C99, однако ключевое слово `__restrict` может использоваться в программах C++ и C.  
  
-   Если используется ключевое слово `__restrict`, компилятор не распространяет свойство переменной no-alias. Иными словами, если переменная с ключевым словом `__restrict` присвоена переменной без ключевого слова `__restrict`, компилятор все еще будет допускать возможность создания псевдонима переменной без ключевого слова __restrict. Этим оно отличается от ключевого слова `restrict` из спецификации C99.  
  
 Как правило, если вы намереваетесь подействовать на поведение всей функции, вместо этого ключевого слова лучше использовать `__declspec ( restrict )`.  
  
 В Visual Studio 2015 и более поздних версий `__restrict` может использоваться для ссылок C++.  
  
> [!NOTE]
>  При использовании для переменной, которая также имеет [volatile](../cpp/volatile-cpp.md) ключевое слово, `volatile` будет иметь приоритет.  
  
## <a name="example"></a>Пример  
  
```  
// __restrict_keyword.c  
// compile with: /LD  
// In the following function, declare a and b as disjoint arrays  
// but do not have same assurance for c and d.  
void sum2(int n, int * __restrict a, int * __restrict b,   
          int * c, int * d) {  
   int i;  
   for (i = 0; i < n; i++) {  
      a[i] = b[i] + c[i];  
      c[i] = b[i] + d[i];  
    }  
}  
  
// By marking union members as __restrict, tell compiler that  
// only z.x or z.y will be accessed in any given scope.  
union z {  
   int * __restrict x;  
   double * __restrict y;  
};  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)
