---
title: "Класс is_pod | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.is_pod"
  - "is_pod"
  - "std::tr1::is_pod"
  - "std.is_pod"
  - "std::is_pod"
  - "type_traits/std::is_pod"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_pod - класс [TR1]"
  - "is_pod"
ms.assetid: d73ebdee-746b-4082-9fa4-2db71432eb0e
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# Класс is_pod
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли тип типом POD.  
  
## Синтаксис  
  
```  
template<class Ty>  
    struct is_pod;  
```  
  
#### Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## Заметки  
 `is_pod<Ty>::value` — `true`, если тип `Ty` — Plain Old Data \(POD\).  В противном случае — `false`.  
  
 К типам POD относятся арифметические типы, типы перечисления, типы указателей и указатели на типы\-члены.  
  
 Квалифицированная версия типа POD также обладает типом POD.  
  
 Массив данных типа POD также имеет тип POD.  
  
 Структура или объединение, все нестатические данные\-члены которого имеют типа POD, также обладает типом POD при соблюдении следующих условий:  
  
-   Нет объявленных пользователем конструкторов.  
  
-   Нет закрытых или защищенных нестатических данных\-членов.  
  
-   Отсутствие базовых классов.  
  
-   Нет виртуальных функций.  
  
-   Нет нестатических данных\-членов ссылочного типа.  
  
-   Нет определяемого пользователем оператора присвоения копирования.  
  
-   Нет определяемого пользователем деструктора.  
  
 Таким образом, можно рекурсивно создавать структуры POD и массивы, содержащие структуры и массивы POD.  
  
## Пример  
  
```  
// std_tr1__type_traits__is_pod.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
struct throws   
    {   
    throws() throw(int)   
        {   
        }   
  
    throws(const throws&) throw(int)   
        {   
        }   
  
    throws& operator=(const throws&) throw(int)   
        {   
        }   
  
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_pod<trivial> == " << std::boolalpha   
        << std::is_pod<trivial>::value << std::endl;   
    std::cout << "is_pod<int> == " << std::boolalpha   
        << std::is_pod<int>::value << std::endl;   
    std::cout << "is_pod<throws> == " << std::boolalpha   
        << std::is_pod<throws>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_pod\<trivial\> \=\= true**  
**is\_pod\<int\> \=\= true**  
**is\_pod\<throws\> \=\= false**   
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)