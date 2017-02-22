---
title: "Структура forward_iterator_tag | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.forward_iterator_tag"
  - "forward_iterator_tag"
  - "std::forward_iterator_tag"
  - "xutility/std::forward_iterator_tag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "forward_iterator_tag - класс"
  - "forward_iterator_tag - структура"
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# Структура forward_iterator_tag
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс, предоставляющий возвращаемый тип для функции **iterator\_category**, представляющую передний итератор.  
  
## Синтаксис  
  
```  
  
   struct forward_iterator_tag  
: public input_iterator_tag {};  
```  
  
## Заметки  
 Классы тега категории используются как компилируют теги для выделения алгоритма.  Функции шаблона необходимо понимать, что самой определенной категории своего аргумента итератора, чтобы его можно было использовать наиболее эффективный алгоритм во время компиляции.  Для каждого типа итератора `Iterator`, `iterator_traits`\<`Iterator`\>**::iterator\_category** должны быть самым указанным тегом категории, описывающий расширение функциональности итератора.  
  
 Тип совпадает с **::iterator\_category** по **iterator**\<**Iter**\>**Iter** описывает объект, который можно использовать как передний итератор.  
  
## Пример  
 В разделе [iterator\_traits](../standard-library/iterator-traits-struct.md) или [random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md) пример использования **iterator\_tag** s.  
  
## Требования  
 **Заголовок:**\<iterator\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Структура input\_iterator\_tag](../standard-library/input-iterator-tag-struct.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)