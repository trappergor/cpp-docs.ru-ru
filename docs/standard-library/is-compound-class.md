---
title: "Класс is_compound | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::is_compound"
  - "is_compound"
  - "std.tr1.is_compound"
  - "std.is_compound"
  - "std::is_compound"
  - "type_traits/std::is_compound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_compound - класс [TR1]"
  - "is_compound"
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# Класс is_compound
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли указанный тип фундаментальным.  
  
## Синтаксис  
  
```  
template<class Ty>  
    struct is_compound;  
```  
  
#### Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## Заметки  
 Экземпляр предиката типа содержит `false`, если тип `Ty` — фундаментальный тип \(т. е., если [is\_fundamental](../standard-library/is-fundamental-class.md)`<``Ty``>` имеет значение `true`\). В противном случае — он имеет значение `true`.  Таким образом, предикат имеет значение `true`, если `Ty` является типом массива, типом функции, указателем на `void`, на объект или функцию, ссылкой, классом, объединением, перечислением или указателем на нестатический член класса или форму *cv\-qualified* одного из них.  
  
## Пример  
  
```  
// std_tr1__type_traits__is_compound.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_compound<trivial> == " << std::boolalpha   
        << std::is_compound<trivial>::value << std::endl;   
    std::cout << "is_compound<int[]> == " << std::boolalpha   
        << std::is_compound<int[]>::value << std::endl;   
    std::cout << "is_compound<int()> == " << std::boolalpha   
        << std::is_compound<int()>::value << std::endl;   
    std::cout << "is_compound<int&> == " << std::boolalpha   
        << std::is_compound<int&>::value << std::endl;   
    std::cout << "is_compound<void *> == " << std::boolalpha   
        << std::is_compound<void *>::value << std::endl;   
    std::cout << "is_compound<int> == " << std::boolalpha   
        << std::is_compound<int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_compound\<trivial\> \=\= true**  
**is\_compound\<int\[\]\> \=\= true**  
**is\_compound\<int\(\)\> \=\= true**  
**is\_compound\<int&\> \=\= true**  
**is\_compound\<void \*\> \=\= true**  
**is\_compound\<int\> \=\= false**   
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Класс is\_class](../standard-library/is-class-class.md)