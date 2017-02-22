---
title: "Класс add_lvalue_reference | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::add_lvalue_reference"
  - "add_lvalue_reference"
  - "type_traits/std::add_lvalue_reference"
  - "std.add_lvalue_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "add_lvalue_reference"
ms.assetid: 9933afc2-ad0d-465d-98fe-7d547fa3efe2
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# Класс add_lvalue_reference
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Делает из типа ссылку на тип.  
  
## Синтаксис  
  
```  
template<class T>  
    struct add_lvalue_reference;  
  
template<class T>  
    using add_lvalue_reference_t = typename add_lvalue_reference<T>::type;  
```  
  
#### Параметры  
 `T`  
 Тип для изменения.  
  
## Заметки  
 Экземпляр модификатора типа содержит модифицированный тип, т. е. `T`, если `T` является ссылкой lvalue, в противном случае — `T&`.  
  
## Пример  
  
```  
#include <type_traits>   
#include <iostream>   
  
using namespace std;  
int main()  
{  
    int val = 0;  
    add_lvalue_reference_t<int> p = (int&)val;  
    p = p;  // to quiet "unused" warning   
    cout << "add_lvalue_reference_t<int> == "  
        << typeid(p).name() << endl;  
  
    return (0);  
}  
```  
  
  **add\_lvalue\_reference\_t\<int\> \=\= int**   
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Класс remove\_reference](../standard-library/remove-reference-class.md)