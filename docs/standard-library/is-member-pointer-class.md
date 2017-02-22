---
title: "Класс is_member_pointer | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::is_member_pointer"
  - "is_member_pointer"
  - "std.tr1.is_member_pointer"
  - "std.is_member_pointer"
  - "std::is_member_pointer"
  - "type_traits/std::is_member_pointer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_member_pointer - класс [TR1]"
  - "is_member_pointer"
ms.assetid: da07ff4e-9ee0-4baa-ad93-1741f10913d1
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс is_member_pointer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если тесты тип указателя на член.  
  
## Синтаксис  
  
```  
template<class Ty>  
    struct is_member_pointer;  
```  
  
#### Параметры  
 `Ty`  
 Тип в запрос.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если тип `Ty` функция указателя на член или объект указателя на член, или формы `cv-qualified` одного из них, в противном случае — значение false.  
  
## Пример  
  
```  
// std_tr1__type_traits__is_member_pointer.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
struct functional   
    {   
    int f();   
    };   
  
int main()   
    {   
    std::cout << "is_member_pointer<trivial *> == "   
        << std::boolalpha   
        << std::is_member_pointer<trivial *>::value   
        << std::endl;   
    std::cout << "is_member_pointer<int trivial::*> == "   
        << std::boolalpha   
        << std::is_member_pointer<int trivial::*>::value   
        << std::endl;   
    std::cout << "is_member_pointer<int (functional::*)()> == "   
        << std::boolalpha   
        << std::is_member_pointer<int (functional::*)()>::value   
        << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_member\_pointer\<trivial \*\> \=\= false**  
**is\_member\_pointer\<int trivial::\*\> \=\= true**  
**is\_member\_pointer\<int \(functional::\*\)\(\)\> \=\= true**   
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Класс is\_member\_function\_pointer](../Topic/is_member_function_pointer%20Class.md)   
 [Класс is\_member\_object\_pointer](../standard-library/is-member-object-pointer-class.md)   
 [Класс is\_pointer](../standard-library/is-pointer-class.md)