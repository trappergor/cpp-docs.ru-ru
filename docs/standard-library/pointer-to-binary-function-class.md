---
title: "Класс pointer_to_binary_function | Microsoft Docs"
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
  - "std::pointer_to_binary_function"
  - "xfunctional/std::pointer_to_binary_function"
  - "pointer_to_binary_function"
  - "std.pointer_to_binary_function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pointer_to_binary_function - класс"
  - "pointer_to_binary_function - функция"
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс pointer_to_binary_function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Преобразование бинарный указатель функции в способную к адаптации бинарную функции.  
  
## Синтаксис  
  
```  
template<class Arg1, class Arg2, class Result>  
   class pointer_to_binary_function   
   : public binary_function <Arg1, Arg2, Result>   
   {  
   public:  
   explicit pointer_to_binary_function(  
      Result (*_pfunc )( Arg1, Arg2 )   
   );  
   Result operator()(  
      Arg1 _Left,   
      Arg2 _Right  
   ) const;  
   };  
```  
  
#### Параметры  
 `_pfunc`  
 Функция бинарная, которое требуется преобразовать.  
  
 `_Left`  
 Левый объект, *\*\_pfunc* называется включен.  
  
 `_Right`  
 Правой *\*\_pfunc* объект, называется включен.  
  
## Возвращаемое значение  
 Класс шаблона сохранить копию **\_pfunc**.  Он определяет свою функцию\-член `operator()` как возвращающий \(\***\_pfunc**\)\(\_*Left*, \_*Right*\).  
  
## Заметки  
 Бинарный указатель функции объект функции и может быть передан в любой алгоритма стандартной библиотеки шаблонов, ожидает бинарная функции в качестве параметра, но не поддерживает к адаптации.  Чтобы использовать ключевое переходникой, например привязка значения в него или использовать их с negator, его следует указывать с вложенными типами **first\_argument\_type**, **second\_argument\_type** и **result\_type**, которые делают возможным такое адаптацию.  Преобразование `pointer_to_binary_function` позволяет переходники функции для работы с бинарными указателями функций.  
  
## Пример  
 Конструктор `pointer_to_binary_function` используется редко напрямую.  В разделе вспомогательную функцию [ptr\_fun](../Topic/ptr_fun%20Function.md) для примера способы объявления и использования предикат переходники `pointer_to_binary_function`.  
  
## Требования  
 **Заголовок:** \<functional\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)