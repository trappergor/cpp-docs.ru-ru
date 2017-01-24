---
title: "Класс is_convertible | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_convertible"
  - "std.tr1.is_convertible"
  - "std::tr1::is_convertible"
  - "std.is_convertible"
  - "std::is_convertible"
  - "type_traits/std::is_convertible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_convertible - класс [TR1]"
  - "is_convertible"
ms.assetid: 75614008-1894-42ea-bd57-974399628536
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс is_convertible
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, можно ли преобразовать один тип в другой.  
  
## Синтаксис  
  
```  
template<class From, class To>  
    struct is_convertible;  
```  
  
#### Параметры  
 `From`  
 Преобразовываемый тип.  
  
 `Ty`  
 Целевой тип преобразования.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если выражение `To to = from;`, где `from` является объектом типа `From`, имеет правильный формат.  
  
## Пример  
  
```  
// std_tr1__type_traits__is_convertible.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_convertible<trivial, int> == " << std::boolalpha   
        << std::is_convertible<trivial, int>::value << std::endl;   
    std::cout << "is_convertible<trivial, trivial> == " << std::boolalpha   
        << std::is_convertible<trivial, trivial>::value << std::endl;   
    std::cout << "is_convertible<char, int> == " << std::boolalpha   
        << std::is_convertible<char, int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_convertible\<trivial, int\> \=\= false**  
**is\_convertible\<trivial, trivial\> \=\= true**  
**is\_convertible\<char, int\> \=\= true**   
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Класс is\_base\_of](../standard-library/is-base-of-class.md)