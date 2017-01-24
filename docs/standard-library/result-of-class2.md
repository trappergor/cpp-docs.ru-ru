---
title: "Класс result_of | Microsoft Docs"
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
  - "functional/std::tr1::result_of"
  - "std::tr1::result_of"
  - "result_of"
  - "std.tr1.result_of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "result_of - класс [TR1]"
ms.assetid: 14ec0040-07f1-45a5-80b5-d0c9f9b00c8f
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс result_of
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Возвращаемый тип создаватього программу\-оболочку вызываемую объекта.  
  
## Синтаксис  
  
```  
template<class Ty>  
    struct result_of {  
    typedef T0 type;  
    };  
```  
  
#### Параметры  
 `Ty`  
 Описание вызова функции \(см. раздел комментария\).  
  
## Заметки  
 Класс шаблона определяет его члена `type` синонимом возвращаемого типа вызова функции extension.vsixmanifest его аргументом `Ty` шаблона.  Аргумент шаблона должен быть в форме `Fty(T1, T2, ..., TN)`, где `Fty` вызываемую тип.  Шаблон определяет возвращаемый тип в соответствии с первой из следующих правил, применяется:  
  
-   если `Fty` указатель на тип `R(*)(U1, U2, ..., UN)`, возвращаемый тип функции `R`;  
  
-   если `Fty` ссылка на тип `R(&)(U1, U2, ..., UN)`, возвращаемый тип функции `R`;  
  
-   если `Fty` тип `R(U1::*)(U2, ..., UN)`, указателем на функцию\-член возвращаемый тип `R`;  
  
-   если `Fty` указатель на тип `R U1::*`, возвращаемый тип элемента данных `R`;  
  
-   если `Fty` класс с typedef `result_type`, возвращаемый тип члена `Fty::result_type`;  
  
-   если `N` 0, \(то есть `Ty` формы `Fty()`\) возвращаемый тип `void`;  
  
-   если `Fty` класс с именем шаблон членов `result`, возвращаемый тип `Fty::result<T1, T2, ..., TN>::type`;  
  
-   во всех остальных случаях ошибка.  
  
## Пример  
  
```  
// std_tr1__functional__result_of.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
double square(double x)   
    {   
    return (x * x);   
    }   
  
template<class Fun,   
    class Arg>   
    void test_result(const Fun& fun, Arg arg)   
    {   
    typename std::result_of<Fun(Arg)>::type val = fun(arg);   
    std::cout << "val == " << val << std::endl;   
    }   
  
int main()   
    {   
    test_result(&square, 3.0);   
  
    return (0);   
    }  
  
```  
  
  **val \=\= 9**   
## Требования  
 **Заголовок:** \<functional\>  
  
 **Пространство имен:** std