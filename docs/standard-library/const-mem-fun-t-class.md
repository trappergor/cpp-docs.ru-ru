---
title: "Класс const_mem_fun_t | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "const_mem_fun_t"
  - "std.const_mem_fun_t"
  - "xfunctional/std::const_mem_fun_t"
  - "std::const_mem_fun_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_mem_fun_t - класс"
ms.assetid: f169d381-019b-4a0e-a9a3-54da6d948270
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# Класс const_mem_fun_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс адаптера, который позволяет функцию\-член const, не принимающего аргументов, для вызова функции в качестве унарного объект инициализирован с аргументом ссылки.  
  
## Синтаксис  
  
```  
template<class Result, class Type>  
   class const_mem_fun_t : public unary_function <Type *, Result>   
   {  
   explicit const_mem_fun_t( Result ( Type::* _Pm )( ) const );  
   Result operator()(  
      const Type* _Pleft  
   ) const;  
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
 Класс шаблона сохранить копию `_Pm`, который должен быть указателем на функцию\-член класса **Тип** в объекте закрытого члена.  Он определяет свою функцию\-член `operator()` как возвращающий \(`_Pleft`\-\>\* `_Pm`\)\(\) **const**.  
  
## Пример  
 Конструктор `const_mem_fun_t` обычно не должен использоваться напрямую; вспомогательная функция `mem_fun` используется для размещения функции\-члены.  В разделе [mem\_fun](../Topic/mem_fun%20Function.md) пример использования переходники функции\-члена.  
  
## Требования  
 **Заголовок:** \<functional\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)