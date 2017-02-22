---
title: "Класс pointer_to_unary_function | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xfunctional/std::pointer_to_unary_function"
  - "pointer_to_unary_function"
  - "std.pointer_to_unary_function"
  - "std::pointer_to_unary_function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pointer_to_unary_function - класс"
  - "pointer_to_unary_function - функция"
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# Класс pointer_to_unary_function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Преобразование унарный указатель функции в способную к адаптации унарную функции.  
  
## Синтаксис  
  
```  
template<class Arg, class Result>  
class pointer_to_unary_function  
    : public unary_function<Arg, Result>   
    {  
    public:  
        explicit pointer_to_unary_function(  
            Result (*_pfunc)(Arg)  
        );  
        Result operator()(  
            Arg _Left  
        ) const;  
    };  
```  
  
#### Параметры  
 `_pfunc`  
 Функция бинарная, которое требуется преобразовать.  
  
 `_Left`  
 Объект, *\*\_pfunc* называется включен.  
  
## Возвращаемое значение  
 Класс шаблона сохранить копию **\_pfunc**.  Он определяет свою функцию\-член `operator()` как возвращающий \(\***\_pfunc**\)\(\_*Left*\).  
  
## Заметки  
 Унарный указатель функции объект функции и может быть передан в любой алгоритма стандартной библиотеки шаблонов, ожидает унарная функции в качестве параметра, но не поддерживает к адаптации.  Чтобы использовать ключевое переходникой, например привязка значения в него или использовать их с negator, его следует указывать с вложенными типами **argument\_type** и **result\_type**, которые делают возможным такое адаптацию.  Преобразование `pointer_to_unary_function` позволяет переходники функции для работы с бинарными указателями функций.  
  
## Пример  
 Конструктор `pointer_to_unary_function` используется редко напрямую.  В разделе вспомогательную функцию [ptr\_fun](../Topic/ptr_fun%20Function.md) для примера способы объявления и использования предикат переходники `pointer_to_unary_function`.  
  
## Требования  
 **Заголовок:** \<functional\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)