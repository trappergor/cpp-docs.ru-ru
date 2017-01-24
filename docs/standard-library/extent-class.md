---
title: "Класс extent | Microsoft Docs"
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
  - "std.tr1.extent"
  - "extent"
  - "std::tr1::extent"
  - "std.extent"
  - "std::extent"
  - "type_traits/std::extent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "extent - класс [TR1]"
  - "extent"
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс extent
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает измерение массива.  
  
## Синтаксис  
  
```  
template<class Ty, unsigned I = 0>  
    struct extent;  
```  
  
#### Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
 `I`  
 Массив, привязанный к запросу.  
  
## Заметки  
 Если `Ty` является типом массива, который имеет по крайней мере `I` измерений, запрос типа содержит число элементов в измерении, заданное `I`.  Если `Ty` не является типом массива или его ранг меньше `I` или если `I` равно нулю и `Ty` имеет тип "массив с неизвестной границей `U`, запрос типа содержит значение 0.  
  
## Пример  
  
```  
// std_tr1__type_traits__extent.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "extent 0 == "   
        << std::extent<int[5][10]>::value << std::endl;   
    std::cout << "extent 1 == "   
        << std::extent<int[5][10], 1>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **extent 0 \=\= 5**  
**extent 1 \=\= 10**   
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Класс remove\_all\_extents](../standard-library/remove-all-extents-class.md)   
 [Класс remove\_extent](../standard-library/remove-extent-class.md)