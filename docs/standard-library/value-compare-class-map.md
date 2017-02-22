---
title: "Класс value_compare (&lt;map&gt;) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::value_compare"
  - "std.value_compare"
  - "map/std::value_compare"
  - "value_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_compare - класс"
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# Класс value_compare (&lt;map&gt;)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предоставляет объект функции, можно сравнивать элементы сопоставления, сравнивая значения ключей для определения относительный порядок в сопоставлении.  
  
## Синтаксис  
  
```  
class value_compare : public binary_function<value_type, value_type, bool>  
{  
public:  
   bool operator()(const value_type& _Left, const value_type& _Right) const;  
   value_compare(key_compare _Pred) : comp(_Pred);  
   protected:  
      key_compare comp;  
};  
```  
  
## Заметки  
 Критерий сравнения предоставленная `value_compare` между **value\_types** всех элементов, который содержит сопоставление между ключами сравнения вызывается из соответствующих элементов вспомогательным разработке класса.  Оператор функции\-члена используется объект **компьютер** типа `key_compare`, хранящиеся в объекте функций, предоставленных `value_compare` сравнил компоненты сортировка\- ключа 2 элементов.  
  
 Для наборов и multisets простые контейнеры, где значения ключа совпадают значения элемента, `value_compare` эквивалентно `key_compare`; для сопоставления и multimaps нет — как значение элемента `pair` типа не совпадать со значением ключа элемента.  
  
## Пример  
 См. пример для [value\_comp](../Topic/map::value_comp.md) пример способы объявления и использования `value_compare`.  
  
## Требования  
 **Заголовок:**\<map\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Структура binary\_function](../Topic/binary_function%20Struct.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)