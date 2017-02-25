---
title: "Класс remove_all_extents | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.remove_all_extents"
  - "std::tr1::remove_all_extents"
  - "remove_all_extents"
  - "std.remove_all_extents"
  - "std::remove_all_extents"
  - "type_traits/std::remove_all_extents"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_all_extents - класс [TR1]"
  - "remove_all_extents"
ms.assetid: 548dc536-82e7-423a-b8c1-443d66d9632e
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# Класс remove_all_extents
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает из типа массива тип, не относящийся к массиву.  
  
## Синтаксис  
  
```  
template<class T>  
    struct remove_all_extents;  
  
template<class T>  
  using remove_all_extents_t = typename remove_all_extents<T>::type;  
```  
  
#### Параметры  
 `T`  
 Тип для изменения.  
  
## Заметки  
 Экземпляр `remove_all_extents<T>` содержит измененный тип, который является типом элемента типа массива `T`, где все измерения массива удалены, или `T`, если `T` не является типом массива.  
  
## Пример  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "remove_all_extents<int> == "   
        << typeid(std::remove_all_extents_t<int>).name()   
        << std::endl;   
    std::cout << "remove_all_extents_t<int[5]> == "   
        << typeid(std::remove_all_extents_t<int[5]>).name()   
        << std::endl;   
    std::cout << "remove_all_extents_t<int[5][10]> == "   
        << typeid(std::remove_all_extents_t<int[5][10]>).name()   
        << std::endl;   
  
    return (0);   
    }  
  
```  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Класс remove\_extent](../standard-library/remove-extent-class.md)