---
title: "Класс add_pointer | Microsoft Docs"
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
  - "std::tr1::add_pointer"
  - "std.tr1.add_pointer"
  - "add_pointer"
  - "std.add_pointer"
  - "std::add_pointer"
  - "type_traits/std::add_pointer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "add_pointer - класс [TR1]"
  - "add_pointer"
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
caps.latest.revision: 22
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс add_pointer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает указатель на тип из указанного типа.  
  
## Синтаксис  
  
```  
template<class Ty>  
    struct add_pointer;  
  
template<class T>  
using add_pointer_t = typename add_pointer<T>::type;  
```  
  
#### Параметры  
 `Ty`  
 Тип для изменения.  
  
## Заметки  
 Тип typedef члена именует тот же тип как `remove_reference<T>::type*`.  
  
 Поскольку его нельзя использовать для создания указателя из ссылки, `add_pointer` удаляет ссылку \(если таковая имеется\) из указанного типа, прежде чем создать указатель на тип.  Следовательно, можно использовать тип с `add_pointer` вне зависимости от того, является ли данный тип ссылкой.  
  
## Пример  
 В следующем примере показано, что `add_pointer` типа аналогичен указателю на данный тип.  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::add_pointer_t<int> *p = (int **)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_pointer_t<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **add\_pointer\_t\<int\> \=\= int \***   
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Класс remove\_pointer](../Topic/remove_pointer%20Class.md)