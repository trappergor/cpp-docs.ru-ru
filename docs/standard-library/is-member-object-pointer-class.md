---
title: "Класс is_member_object_pointer | Microsoft Docs"
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
  - "is_member_object_pointer"
  - "std.tr1.is_member_object_pointer"
  - "std::tr1::is_member_object_pointer"
  - "std.is_member_object_pointer"
  - "std::is_member_object_pointer"
  - "type_traits/std::is_member_object_pointer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_member_object_pointer - класс [TR1]"
  - "is_member_object_pointer"
ms.assetid: 64f9cdf3-4621-4310-a076-a7bc986926b9
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс is_member_object_pointer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли тип указателем на объект члена.  
  
## Синтаксис  
  
```  
template<class Ty>  
    struct is_member_object_pointer;  
```  
  
#### Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если тип `Ty` является указателем на объект члена или указателем `cv-qualified` на объект члена, в противном случае — значение false.  Обратите внимание, что `is_member_object_pointer` содержит значение false, если `Ty` является указателем на функцию\-член.  
  
## Пример  
  
```  
// std_tr1__type_traits__is_member_object_pointer.cpp   
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
    std::cout << "is_member_object_pointer<trivial *> == "   
        << std::boolalpha   
        << std::is_member_object_pointer<trivial *>::value   
        << std::endl;   
    std::cout << "is_member_object_pointer<int trivial::*> == "   
        << std::boolalpha   
        << std::is_member_object_pointer<int trivial::*>::value   
        << std::endl;   
    std::cout << "is_member_object_pointer<int (functional::*)()> == "   
        << std::boolalpha   
        << std::is_member_object_pointer<int (functional::*)()>::value   
        << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_member\_object\_pointer\<trivial \*\> \=\= false**  
**is\_member\_object\_pointer\<int trivial::\*\> \=\= true**  
**is\_member\_object\_pointer\<int \(functional::\*\)\(\)\> \=\= false**   
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Класс is\_member\_pointer](../standard-library/is-member-pointer-class.md)