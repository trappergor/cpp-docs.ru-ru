---
title: "logical_not (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::logical_not"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "logical_not - функция [STL/CLR]"
ms.assetid: 32a2c6e2-1c58-41ac-8827-f3ee5adfe81d
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# logical_not (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описание класса шаблона функтором, при вызове возвращает значение true только в том случае, если все его аргумент, как false.  Он используется определяется объект функции с точки зрения его типа аргумента.  
  
## Синтаксис  
  
```  
template<typename Arg>  
    ref class logical_not  
    { // wrap operator()  
public:  
    typedef Arg argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        argument_type, result_type>  
        delegate_type;  
  
    logical_not();  
    logical_not(logical_not<Arg> %right);  
  
    result_type operator()(argument_type left);  
    operator delegate_type^();  
    };  
```  
  
#### Параметры  
 Аргумент  
 Тип аргументов.  
  
## Функции\-члены  
  
|Определение типа|Описание|  
|----------------------|--------------|  
|argument\_type|Тип аргумента функтором.|  
|delegate\_type|Тип универсального метод\-делегата.|  
|result\_type|Тип результата функтором.|  
  
|Член|Описание|  
|----------|--------------|  
|logical\_not|Построение функтором.|  
  
|Оператор|Описание|  
|--------------|--------------|  
|operator\(\)|Вычисляет нужную функцию.|  
|delegate\_type^ оператора|Возвращает функтором делегату.|  
  
## Заметки  
 Описание класса шаблона функтором от аргумента.  Он определяет оператор `operator()` члена, что, когда объект вызывается как функция, он возвращает значение true, только если его аргумент, как false.  
  
 Можно также передать объект в качестве аргумента функции, тип которого `delegate_type^` и он будет преобразован соответствующим образом.  
  
## Пример  
  
```  
// cliext_logical_not.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(0);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 0"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c3.begin(), cliext::logical_not<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 0**  
 **0 1**   
## Требования  
 **Заголовок:**\<cliext\/functional\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [negate](../Topic/negate%20\(STL-CLR\).md)