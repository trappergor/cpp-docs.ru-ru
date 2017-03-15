---
title: "equal_to (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::equal_to"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "equal_to - функция [STL/CLR]"
ms.assetid: 9dd6e27d-e695-470f-b7a7-19a6db970ee5
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# equal_to (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описание класса шаблона функтором, возвращает значение true, вызывается, только если первый аргумент равен второму.  Он используется определяется объект функции с точки зрения его типа аргумента.  
  
## Синтаксис  
  
```  
template<typename Arg>  
    ref class equal_to  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    equal_to();  
    equal_to(equal_to<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### Параметры  
 Аргумент  
 Тип аргументов.  
  
## Функции\-члены  
  
|Определение типа|Описание|  
|----------------------|--------------|  
|delegate\_type|Тип универсального метод\-делегата.|  
|first\_argument\_type|Тип первого аргумента функтором.|  
|result\_type|Тип результата функтором.|  
|second\_argument\_type|Тип второго аргумента функтором.|  
  
|Член|Описание|  
|----------|--------------|  
|equal\_to|Построение функтором.|  
  
|Оператор|Описание|  
|--------------|--------------|  
|operator\(\)|Вычисляет нужную функцию.|  
|оператор delegate\_type^\(\)|Возвращает функтором делегату.|  
  
## Заметки  
 Описание класса шаблона функтором 2 — аргумента.  Он определяет оператор `operator()` члена, что, когда объект вызывается как функция возвращается только значение true, если первый аргумент равен второму.  
  
 Можно также передать объект в качестве аргумента функции, тип которого `delegate_type^` и он будет преобразован соответствующим образом.  
  
## Пример  
  
```  
// cliext_equal_to.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(4);   
    c2.push_back(4);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 4 4"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::equal_to<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 3**  
 **4 4**  
 **1 0**   
## Требования  
 **Заголовок:**\<cliext\/functional\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [not\_equal\_to](../dotnet/not-equal-to-stl-clr.md)