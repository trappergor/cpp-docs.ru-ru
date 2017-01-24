---
title: "Класс bool_constant класс integral_constant | Microsoft Docs"
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
  - "std.tr1.integral_constant"
  - "integral_constant"
  - "std::tr1::integral_constant"
  - "std.integral_constant"
  - "std::integral_constant"
  - "type_traits/std::integral_constant"
  - "std.bool_constant"
  - "std::bool_constant"
  - "type_traits/std::bool_constant"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "integral_constant - класс [TR1]"
  - "integral_constant"
  - "bool_constant"
ms.assetid: 11c002c6-4d31-4042-9341-f2543f43e108
caps.latest.revision: 23
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс bool_constant класс integral_constant
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Делает из типа и значения постоянным целым.  
  
## Синтаксис  
  
```  
template <class T, T v>  
    struct integral_constant {  
        static constexpr T value = v;  
        typedef T value_type;  
        typedef integral_constant<T, v> type;  
        constexpr operator value_type() const noexcept { return (value); }  
        constexpr value_type operator()() const noexcept { return (value); }  
    };  
  
template <bool v>  
    using bool_constant = integral_constant<bool, v>;  
  
```  
  
#### Параметры  
 `T`  
 Тип константы.  
  
 `v`  
 Значение константы.  
  
## Заметки  
 `integral_constant` Класс шаблона, когда определен с целочисленным типом `T` и значение `v` этого типа, представляющий объект, который содержит константу, целочисленного типа с указанным значением. Член с именем `type` является псевдонимом для специализации тип созданного шаблона и `value` член содержит значение `v` используется для создания специализации.  
  
 `bool_constant` Класс шаблона является явная частичная специализация `integral_constant` использующий `bool` как `T` аргумент.  
  
## Пример  
  
```cpp  
// std__type_traits__integral_constant.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "integral_constant<int, 5> == "   
        << std::integral_constant<int, 5>::value << std::endl;   
    std::cout << "integral_constant<bool, false> == " << std::boolalpha   
        << std::integral_constant<bool, false>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
integral_constant < int 5 > == 5 integral_constant < bool, false > == false  
```  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Определение типа \(Typedef\) false\_type](../Topic/false_type%20Typedef.md)   
 [Определение типа \(Typedef\) true\_type](../Topic/true_type%20Typedef.md)