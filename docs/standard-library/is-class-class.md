---
title: "Класс is_class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_class"
  - "std::tr1::is_class"
  - "std.tr1.is_class"
  - "std.is_class"
  - "std::is_class"
  - "type_traits/std::is_class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_class - класс [TR1]"
  - "is_class"
ms.assetid: 96fc34a3-a81b-4ec6-b7fb-baafde1a0f4e
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс is_class
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли тип классом.  
  
## Синтаксис  
  
```  
template<class Ty>  
    struct is_class;  
```  
  
#### Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если тип `Ty` является типом, определенным как `class`, `struct` или форма `cv-qualified` одного из них, в противном случае — значение false.  
  
## Пример  
  
```  
// std_tr1__type_traits__is_class.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_class<trivial> == " << std::boolalpha   
        << std::is_class<trivial>::value << std::endl;   
    std::cout << "is_class<int> == " << std::boolalpha   
        << std::is_class<int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_class\<trivial\> \=\= true**  
**is\_class\<int\> \=\= false**   
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Класс is\_compound](../standard-library/is-compound-class.md)   
 [Класс is\_union](../standard-library/is-union-class.md)