---
title: "logical_and (STL/CLR) | Microsoft Docs"
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
  - "cliext::logical_and"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "logical_and - функция [STL/CLR]"
ms.assetid: ae103802-11e0-4060-a4f3-4f6fdc209e7c
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# logical_and (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описание класса шаблона функтором, при вызове возвращает значение true, если и только первый и второй аргумент тест как true.  Он используется определяется объект функции с точки зрения его типа аргумента.  
  
## Синтаксис  
  
```  
template<typename Arg>  
    ref class logical_and  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    logical_and();  
    logical_and(logical_and<Arg>% right);  
  
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
|logical\_and|Построение функтором.|  
  
|Оператор|Описание|  
|--------------|--------------|  
|operator\(\)|Вычисляет нужную функцию.|  
|delegate\_type^ оператора|Возвращает функтором делегату.|  
  
## Заметки  
 Описание класса шаблона функтором 2 — аргумента.  Он определяет оператор `operator()` члена, что, когда объект вызывается как функция, он возвращает значение true, если и только первый и второй аргумент тест как true.  
  
 Можно также передать объект в качестве аргумента функции, тип которого `delegate_type^` и он будет преобразован соответствующим образом.  
  
## Пример  
  
```  
// cliext_logical_and.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(2);   
    c1.push_back(0);   
    Myvector c2;   
    c2.push_back(3);   
    c2.push_back(0);   
    Myvector c3(2, 0);   
  
// display initial contents " 1 0" and " 1 0"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::logical_and<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **2 0**  
 **3 0**  
 **1 0**   
## Требования  
 **Заголовок:**\<cliext\/functional\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [logical\_or](../Topic/logical_or%20\(STL-CLR\).md)