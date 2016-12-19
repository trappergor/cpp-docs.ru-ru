---
title: "Структура output_iterator_tag | Microsoft Docs"
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
  - "std::output_iterator_tag"
  - "output_iterator_tag"
  - "xutility/std::output_iterator_tag"
  - "std.output_iterator_tag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "output_iterator_tag - класс"
  - "output_iterator_tag - структура"
ms.assetid: c23a4331-b069-4fa0-9c3a-1c9be7095553
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Структура output_iterator_tag
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс, предоставляющий тип возвращаемого значения для функции **iterator\_category**, которая представляет собой итератор вывода.  
  
## Синтаксис  
  
```  
  
struct output_iterator_tag {};  
  
```  
  
## Заметки  
 Классы категории тегов используются как компилировать тегов для выбора алгоритма. Функция шаблона должен найти наиболее определенной категории аргумента итератора, чтобы можно было использовать наиболее эффективный алгоритм во время компиляции. Для каждого итератора типа `Iterator`, `iterator_traits`\<`Iterator`\>**:: iterator\_category** должен быть определен наиболее конкретной категории тег, который описывает поведение итератора.  
  
 Тип является таким же, как **итератор**\<**Iter**\>**:: iterator\_category** при **Iter** описывает объект, который можно использовать как итератор вывода.  
  
 Этот тег не параметризуется по `value_type` или `difference_type` для итератора, как и в случае с другими тегами итератора, так как итераторы выходные данные не имеют либо `value_type` или `difference_type`.  
  
## Пример  
 В разделе [iterator\_traits](../standard-library/iterator-traits-struct.md) или [random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md) пример использования **iterator\_tag**s.  
  
## Требования  
 **Заголовок:** \<iterator\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)