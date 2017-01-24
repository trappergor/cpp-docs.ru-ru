---
title: "divides (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::divides"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "divides - функция [STL/CLR]"
ms.assetid: 4c36026a-02ba-475d-af68-854599647f4b
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# divides (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описание класса шаблона функтором, при вызове возвращает первый аргумент разделенный вторым.  Он используется определяется объект функции с точки зрения его типа аргумента.  
  
## Синтаксис  
  
```  
template<typename Arg>  
    ref class divides  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef Arg result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    divides();  
    divides(divides<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### Параметры  
 Аргумент  
 Тип аргументов и возвращаемого значения.  
  
## Функции\-члены  
  
|Определение типа|Описание|  
|----------------------|--------------|  
|delegate\_type|Тип универсального метод\-делегата.|  
|first\_argument\_type|Тип первого аргумента функтором.|  
|result\_type|Тип результата функтором.|  
|second\_argument\_type|Тип второго аргумента функтором.|  
  
|Член|Описание|  
|----------|--------------|  
|делит|Построение функтором.|  
  
|Оператор|Описание|  
|--------------|--------------|  
|operator\(\)|Вычисляет нужную функцию.|  
|оператор delegate\_type^\(\)|Возвращает функтором делегату.|  
  
## Заметки  
 Описание класса шаблона функтором 2 — аргумента.  Он определяет оператор `operator()` члена, что, когда объект вызывается как функция возвращается первый аргумент разделенный вторым.  
  
 Можно также передать объект в качестве аргумента функции, тип которого `delegate_type^` и он будет преобразован соответствующим образом.  
  
## Пример  
  
```  
// cliext_divides.cpp   
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
    c2.push_back(2);   
    c2.push_back(1);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 2 1"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::divides<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 3**  
 **2 1**  
 **2 3**   
## Требования  
 **Заголовок:**\<cliext\/functional\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [остатка от деления](../dotnet/modulus-stl-clr.md)   
 [multiplies](../Topic/multiplies%20\(STL-CLR\).md)