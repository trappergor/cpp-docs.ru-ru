---
title: "Структура input_iterator_tag | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "input_iterator_tag"
  - "std.input_iterator_tag"
  - "std::input_iterator_tag"
  - "xutility/std::input_iterator_tag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "input_iterator_tag - класс"
  - "input_iterator_tag - структура"
ms.assetid: ad68a4c6-f315-4ce1-8b74-c1fc71bd1577
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# Структура input_iterator_tag
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс, предоставляющий возвращаемый тип для функции **iterator\_category**, представляющую итератор.  
  
## Синтаксис  
  
```  
  
struct input_iterator_tag {};  
  
```  
  
## Заметки  
 Классы тега категории используются как компилируют теги для выделения алгоритма.  Функции шаблона необходимо найти наиболее определенной категории своего аргумента итератора, чтобы он мог использовать наиболее эффективный алгоритм во время компиляции.  Для каждого типа итератора `Iterator`, `iterator_traits`\<`Iterator`\>**::iterator\_category** должны быть самым указанным тегом категории, описывающий расширение функциональности итератора.  
  
 Тип совпадает с **::iterator\_category** по **iterator**\<**Iter**\>**Iter** описывает объект, который можно использовать как итератор.  
  
## Пример  
 В разделе [iterator\_traits](../standard-library/iterator-traits-struct.md) или [random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md) пример использования **iterator\_tag** s.  
  
## Требования  
 **Заголовок:**\<iterator\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)