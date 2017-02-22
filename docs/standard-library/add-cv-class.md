---
title: "Класс add_cv | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.add_cv"
  - "add_cv"
  - "std::tr1::add_cv"
  - "std.add_cv"
  - "std::add_cv"
  - "type_traits/std::add_cv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "add_cv - класс [TR1]"
  - "add_cv"
ms.assetid: a5572c78-a097-45d7-b476-ed4876889dea
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# Класс add_cv
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает константный\/долговременный тип из типа.  
  
## Синтаксис  
  
```  
template<class Ty>  
    struct add_cv;  
  
template<class T>  
using add_cv_t = typename add_cv<T>::type;  
```  
  
#### Параметры  
 `Ty`  
 Тип для изменения.  
  
## Заметки  
 Экземпляр модификатора типа содержит модифицированный тип [Класс add\_volatile](../standard-library/add-volatile-class.md)`<` [Класс add\_const](../Topic/add_const%20Class.md)`<Ty> >`.  
  
## Пример  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::add_cv_t<int> *p = (const volatile int *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_cv<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **add\_cv\_t\<int\> \=\= int**   
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Класс remove\_const](../standard-library/remove-const-class.md)   
 [Класс remove\_volatile](../Topic/remove_volatile%20Class.md)