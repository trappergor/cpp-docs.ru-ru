---
title: "Класс const_mem_fun1_t | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.const_mem_fun1_t"
  - "xfunctional/std::const_mem_fun1_t"
  - "std::const_mem_fun1_t"
  - "const_mem_fun1_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_mem_fun1_t - класс"
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# Класс const_mem_fun1_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс адаптера, который позволяет функцию\-член **const**, который принимает один аргумент, назначив как бинарный инициализированный объект функции с аргументом указателя.  
  
## Синтаксис  
  
```  
template<class Result, class Type, class Arg>  
   class const_mem_fun1_t  
      : public binary_function<const Type *, Arg, Result>   
   {  
   explicit const_mem_fun1_t( Result ( Type::* _Pm )( Arg ) const );  
   Result operator()(  
      const Type* _Pleft,   
      Arg _Right  
   ) const;  
   };  
```  
  
#### Параметры  
 `_Pm`  
 Является указателем на функцию\-член класса **Тип**, чтобы преобразовать объект функции.  
  
 `_Pleft`  
 Объект **const**, `_Pm` вызывается функция\-член включен.  
  
 `_Right`  
 Аргумент, который указан в `_Pm`.  
  
## Возвращаемое значение  
 Способная к адаптации бинарная функции.  
  
## Заметки  
 Класс шаблона сохранить копию `_Pm`, который должен быть указателем на функцию\-член класса **Тип** в объекте закрытого члена.  Он определяет свою функцию\-член `operator()` как возвращающий \(**\_Pleft**\-\>\* *Pm\)\(***Right**\) **const**.  
  
## Пример  
 Конструктор `const_mem_fun1_t` обычно не должен использоваться напрямую; вспомогательная функция `mem_fun` используется для размещения функции\-члены.  В разделе [mem\_fun](../Topic/mem_fun%20Function.md) пример использования переходники функции\-члена.  
  
## Требования  
 **Заголовок:** \<functional\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)