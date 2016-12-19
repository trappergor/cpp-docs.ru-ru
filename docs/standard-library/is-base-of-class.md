---
title: "Класс is_base_of | Microsoft Docs"
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
  - "std.tr1.is_base_of"
  - "is_base_of"
  - "std::tr1::is_base_of"
  - "std.is_base_of"
  - "std::is_base_of"
  - "type_traits/std::is_base_of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_base_of - класс [TR1]"
  - "is_base_of"
ms.assetid: 436f6213-1d4c-4ffc-a588-fc7c4887dd86
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс is_base_of
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли один тип базовым для другого.  
  
## Синтаксис  
  
```  
template<class Base, class Derived>  
    struct is_base_of;  
```  
  
#### Параметры  
 `Base`  
 Базовый класс для проверки.  
  
 `Derived`  
 Производный тип для проверки.  
  
## Заметки  
 Экземпляр предиката типа имеет значение true, если тип `Base` является базовым классом для типа `Derived`, в противном случае — значение false.  
  
## Пример  
  
```  
  
#include <type_traits>   
#include <iostream>   
  
struct base   
    {   
    int val;   
    };   
  
struct derived   
    : public base   
    {   
    };   
  
int main()   
    {   
    std::cout << "is_base_of<base, base> == " << std::boolalpha   
        << std::is_base_of<base, base>::value << std::endl;   
    std::cout << "is_base_of<base, derived> == " << std::boolalpha   
        << std::is_base_of<base, derived>::value << std::endl;   
    std::cout << "is_base_of<derived, base> == " << std::boolalpha   
        << std::is_base_of<derived, base>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_base\_of\<base, base\> \=\= true**  
**is\_base\_of\<base, derived\> \=\= true**  
**is\_base\_of\<derived, base\> \=\= false**   
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Класс is\_convertible](../standard-library/is-convertible-class.md)