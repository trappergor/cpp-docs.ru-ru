---
title: "Класс add_rvalue_reference | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "type_traits/std::add_rvalue_reference"
  - "std::add_rvalue_reference"
  - "add_rvalue_reference"
  - "std.add_rvalue_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс add_rvalue_reference"
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Класс add_rvalue_reference
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает ссылочный тип rvalue параметра шаблона, если он является типом объекта или функции. В противном случае — из\-за семантики сворачивания ссылок, тип является таким же, как параметр шаблона.  
  
## Синтаксис  
  
```cpp  
template<class T>  
    struct add_rvalue_reference;  
  
template<class T>  
    using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;  
```  
  
#### Параметры  
 T  
 Тип для изменения.  
  
## Заметки  
 `add_rvalue_reference` Класс содержит член с именем `type`, который является псевдонимом для типа rvalue ссылается на параметр шаблона `T`. Семантика сворачивания ссылок подразумевают, что, для типов без объектов и функции, не являющейся `T`, `T&&` — `T`. Например, если `T` является типом ссылки lvalue  `add_rvalue_reference<T>::type` является ссылочным типом lvalue, а не ссылка rvalue.  
  
 Для удобства \< type\_traits \> определяет шаблон вспомогательных `add_rvalue_reference_t`, псевдонимы `type` членом `add_rvalue_reference`.  
  
## Пример  
 Данный пример кода использует static\_assert, чтобы показать, как ссылочные типы rvalue создаются с помощью `add_rvalue_reference` и `add_rvalue_reference_t`, и как результат `add_rvalue_reference` ссылки lvalue типа не ссылка rvalue, но сворачивается до типа ссылки lvalue.  
  
```cpp  
// ex_add_rvalue_reference.cpp  
// Build by using: cl /EHsc /W4 ex_add_rvalue_reference.cpp  
#include <type_traits>   
#include <iostream>   
#include <string>  
  
using namespace std;  
int main()  
{  
    static_assert(is_same<add_rvalue_reference<string>::type, string&&>::value,   
        "Expected add_rvalue_reference_t<string> to be string&&");  
    static_assert(is_same<add_rvalue_reference_t<string*>, string*&&>::value,   
        "Expected add_rvalue_reference_t<string*> to be string*&&");  
    static_assert(is_same<add_rvalue_reference<string&>::type, string&>::value,   
        "Expected add_rvalue_reference_t<string&> to be string&");  
    static_assert(is_same<add_rvalue_reference_t<string&&>, string&&>::value,   
        "Expected add_rvalue_reference_t<string&&> to be string&&");  
    cout << "All static_assert tests of add_rvalue_reference passed." << endl;  
    return 0;  
}  
  
/*Output:  
All static_assert tests of add_rvalue_reference passed.  
*/  
```  
  
## Требования  
 Заголовок: \<type\_traits\> Пространство имен: std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Класс add\_lvalue\_reference](../standard-library/add-lvalue-reference-class.md)   
 [Класс is\_rvalue\_reference](../Topic/is_rvalue_reference%20Class.md)