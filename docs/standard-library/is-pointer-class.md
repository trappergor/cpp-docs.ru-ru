---
title: "Класс is_pointer | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.is_pointer"
  - "is_pointer"
  - "std::tr1::is_pointer"
  - "std.is_pointer"
  - "std::is_pointer"
  - "type_traits/std::is_pointer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_pointer - класс [TR1]"
  - "is_pointer"
ms.assetid: 44e0a403-7241-4e0a-8922-32877bcb9a4c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс is_pointer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли тип указателем.  
  
## Синтаксис  
  
```  
template<class Ty>  
    struct is_pointer;  
```  
  
#### Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если тип `Ty` является указателем на `void`, указателем на объект, указателем на функцию или формой `cv-qualified` одного из них. В противном случае — значение false.  Обратите внимание, что `is_pointer` содержит значение false, если `Ty` является указателем на член или функцию\-член.  
  
## Пример  
  
```  
// std_tr1__type_traits__is_pointer.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_pointer<trivial> == " << std::boolalpha   
        << std::is_pointer<trivial>::value << std::endl;   
    std::cout << "is_pointer<int trivial::*> == " << std::boolalpha   
        << std::is_pointer<int trivial::*>::value << std::endl;   
    std::cout << "is_pointer<trivial *> == " << std::boolalpha   
        << std::is_pointer<trivial *>::value << std::endl;   
    std::cout << "is_pointer<int> == " << std::boolalpha   
        << std::is_pointer<int>::value << std::endl;   
    std::cout << "is_pointer<int *> == " << std::boolalpha   
        << std::is_pointer<int *>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_pointer\<trivial\> \=\= false**  
**is\_pointer\<int trivial::\*\> \=\= false**  
**is\_pointer\<trivial \*\> \=\= true**  
**is\_pointer\<int\> \=\= false**  
**is\_pointer\<int \*\> \=\= true**   
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Класс is\_member\_pointer](../standard-library/is-member-pointer-class.md)   
 [Класс is\_reference](../Topic/is_reference%20Class.md)