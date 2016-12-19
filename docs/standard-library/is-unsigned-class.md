---
title: "Класс is_unsigned | Microsoft Docs"
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
  - "std::tr1::is_unsigned"
  - "is_unsigned"
  - "std.tr1.is_unsigned"
  - "std.is_unsigned"
  - "std::is_unsigned"
  - "type_traits/std::is_unsigned"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_unsigned - класс [TR1]"
  - "is_unsigned"
ms.assetid: ba5bec3d-796b-4e54-8595-a3941ec6a8dc
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс is_unsigned
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли тип целочисленным типом без знака.  
  
## Синтаксис  
  
```  
template<class Ty>  
    struct is_unsigned;  
```  
  
#### Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если тип `Ty` является целочисленным типом без знака или целочисленным типом без знака `cv-qualified`. В противном случае он содержит значение false.  
  
## Пример  
  
```  
// std_tr1__type_traits__is_unsigned.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_unsigned<trivial> == " << std::boolalpha   
        << std::is_unsigned<trivial>::value << std::endl;   
    std::cout << "is_unsigned<int> == " << std::boolalpha   
        << std::is_unsigned<int>::value << std::endl;   
    std::cout << "is_unsigned<unsigned int> == " << std::boolalpha   
        << std::is_unsigned<unsigned int>::value << std::endl;   
    std::cout << "is_unsigned<float> == " << std::boolalpha   
        << std::is_unsigned<float>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_unsigned\<trivial\> \=\= false**  
**is\_unsigned\<int\> \=\= false**  
**is\_unsigned\<unsigned int\> \=\= true**  
**is\_unsigned\<float\> \=\= false**   
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Класс is\_signed](../Topic/is_signed%20Class.md)