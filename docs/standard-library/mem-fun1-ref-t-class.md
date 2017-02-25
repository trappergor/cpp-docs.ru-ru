---
title: "Класс mem_fun1_ref_t | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xfunctional/std::mem_fun1_ref_t"
  - "std::mem_fun1_ref_t"
  - "mem_fun1_ref_t"
  - "std.mem_fun1_ref_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mem_fun1_ref_t - класс"
ms.assetid: 7d6742f6-19ba-4523-b3c8-0e5b8f11464f
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# Класс mem_fun1_ref_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс адаптера, который позволяет функцию\-член **non\_const**, который принимает один аргумент, назначив как бинарный инициализированный объект функции с аргументом ссылки.  
  
## Синтаксис  
  
```  
template<class Result, class Type, class Arg>  
   class mem_fun1_ref_t : public binary_function<Type, Arg, Result> {  
      explicit mem_fun1_ref_t(  
         Result (Type::* _Pm )( Arg )  
      );  
      Result operator()(  
         Type& _Left,   
         Arg _Right  
      ) const;  
   };  
```  
  
#### Параметры  
 `_Pm`  
 Является указателем на функцию\-член класса **Тип**, чтобы преобразовать объект функции.  
  
 `_Left`  
 Объект, `_Pm` вызывается функция\-член включен.  
  
 `_Right`  
 Аргумент, который указан в `_Pm`.  
  
## Возвращаемое значение  
 Способная к адаптации бинарная функции.  
  
## Заметки  
 Класс шаблона сохранить копию `_Pm`, который должен быть указателем на функцию\-член класса **Тип** в объекте закрытого члена.  Он определяет свою функцию\-член `operator()` как возвращающий \(**\_Left**.\* `_Pm`\)\(**\_Right**\).  
  
## Пример  
 Конструктор `mem_fun1_ref_t` обычно не должен использоваться напрямую; вспомогательная функция `mem_fun_ref` используется для размещения функции\-члены.  В разделе [mem\_fun\_ref](../Topic/mem_fun_ref%20Function.md) пример использования переходники функции\-члена.  
  
## Требования  
 **Заголовок:** \<functional\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)