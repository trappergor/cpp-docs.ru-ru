---
title: "Класс is_union | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_union"
  - "std::tr1::is_union"
  - "std.tr1.is_union"
  - "std.is_union"
  - "std::is_union"
  - "type_traits/std::is_union"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_union - класс [TR1]"
  - "is_union"
ms.assetid: 80eda256-40b8-4db5-9ac1-d58bb8032a3e
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс is_union
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли тип объединением.  
  
## Синтаксис  
  
```  
template<class Ty>  
    struct is_union;  
```  
  
#### Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если тип `Ty` является типом объединения или формой `cv-qualified` типа объединения, в противном случае — значение false.  
  
## Пример  
  
```  
// std_tr1__type_traits__is_union.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
union ints   
    {   
    int in;   
    long lo;   
    };   
  
int main()   
    {   
    std::cout << "is_union<trivial> == " << std::boolalpha   
        << std::is_union<trivial>::value << std::endl;   
    std::cout << "is_union<int> == " << std::boolalpha   
        << std::is_union<int>::value << std::endl;   
    std::cout << "is_union<ints> == " << std::boolalpha   
        << std::is_union<ints>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_union\<trivial\> \=\= false**  
**is\_union\<int\> \=\= false**  
**is\_union\<ints\> \=\= true**   
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Класс is\_class](../standard-library/is-class-class.md)