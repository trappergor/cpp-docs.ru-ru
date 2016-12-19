---
title: "Класс mem_fun_t | Microsoft Docs"
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
  - "mem_fun_t"
  - "xfunctional/std::mem_fun_t"
  - "std::mem_fun_t"
  - "std.mem_fun_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mem_fun_t - класс"
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс mem_fun_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс адаптера, который позволяет функцию\-член **non\_const**, не принимающего аргументов, для вызова функции в качестве унарного объект инициализирован с аргументом указателя.  
  
## Синтаксис  
  
```  
template<class Result, class Type>  
   class mem_fun_t : public unary_function<Type *, Result> {  
      explicit mem_fun_t(Result ( Type::*_Pm )( ) );  
      Result operator()( Type* _Pleft ) const;  
   };  
```  
  
#### Параметры  
 `_Pm`  
 Является указателем на функцию\-член класса **Тип**, чтобы преобразовать объект функции.  
  
 `_Pleft`  
 Объект, `_Pm` вызывается функция\-член включен.  
  
## Возвращаемое значение  
 Способная к адаптации унарная функции.  
  
## Заметки  
 Класс шаблона сохранить копию `_Pm`, который должен быть указателем на функцию\-член класса **Тип** в объекте закрытого члена.  Он определяет функцию\-член `operator()` как возвращающий \(`_Pleft`\-\>\* `_Pm`\)\( \).  
  
## Пример  
 Конструктор `mem_fun_t` обычно не должен использоваться напрямую; вспомогательная функция `mem_fun` используется для размещения функции\-члены.  В разделе [mem\_fun](../Topic/mem_fun%20Function.md) пример использования переходники функции\-члена.  
  
## Требования  
 **Заголовок:** \<functional\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<functional\>](../standard-library/functional.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)