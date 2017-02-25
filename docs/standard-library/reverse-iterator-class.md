---
title: "Класс reverse_iterator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "reverse_iterator"
  - "std::reverse_iterator"
  - "std.reverse_iterator"
  - "xutility/std::reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reverse_iterator - класс"
ms.assetid: c0b34d04-ae9a-4999-9aff-28b313897ffa
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# Класс reverse_iterator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс шаблона является адаптером итератора, описывающим объект обратного итератора, поведение которого аналогично поведению итератора произвольного доступа или двунаправленного итератора, но в обратном порядке.  Он включает прохождение через диапазон в обратном порядке.  
  
## Синтаксис  
  
```  
template <class RandomIterator>  
class reverse_iterator  
```  
  
#### Параметры  
 RandomIterator  
 Тип, представляющий итератор для адаптации к применению в обратном порядке.  
  
## Заметки  
 Существующие контейнеры стандартной библиотеки шаблонов также задают типы `reverse_iterator` и `const_reverse_iterator` и обладают функциями\-членами `rbegin` и `rend`, которые возвращают обратные итераторы.  Эти итераторы обладают семантикой перезаписи.  Адаптер `reverse_iterator` дополняет эти функции, поскольку предоставляет семантику вставки и может также использоваться в сочетании с потоками.  
  
 Итераторы `reverse_iterator`, требующие двунаправленного итератора, не должны обращаться к функциям\-членам `operator+=`, `operator+`, `operator-=`, `operator-` или `operator[]`, поскольку данные функции\-члены могут использоваться только в сочетании с итераторами произвольного доступа.  
  
 Если диапазон итератора — \[`_First`, \_Last\), где квадратная скобка слева обозначает включение в диапазон элемента \_*First*, а круглая скобка справа — включение всех элементов до элемента \_*Left*  за исключением самого элемента \_*Left* .  Те же элементы будут включены в обращенную последовательность \[**rev** – `_First`, **rev** – \_*Left*\); поэтому если элемент \_*Left* на единицу превышает последний элемент в последовательности, то первый элемент **rev** – \_*First* в обращенной последовательности указывает на элемент \*\(\_*Left* – 1 \).  Идентификатор, который связывает все обратные итераторы с их базовыми итераторами:  
  
 &\*\(**reverse\_iterator** \( *i* \) \) \=\= &\*\( *i* – 1 \).  
  
 На практике это означает, что в обращенной последовательности reverse\_iterator будет ссылаться на элемент, позиция которого на единицу превышает позицию элемента, на который итератор ссылается в исходной последовательности \(т. е. находится справа от данного элемента\).  Поэтому если итератор обращался к элементу 6 в последовательности \(2, 4, 6, 8\), то итератор `reverse_iterator` будет обращаться к элементу 4 в обращенной последовательности \(8, 6, 4, 2\).  
  
### Конструкторы  
  
|||  
|-|-|  
|[reverse\_iterator](../Topic/reverse_iterator::reverse_iterator.md)|Формирование итератора `reverse_iterator` по умолчанию или итератора `reverse_iterator` из базового итератора.|  
  
### Определения типов  
  
|||  
|-|-|  
|[difference\_type](../Topic/reverse_iterator::difference_type.md)|Тип, обеспечивающий разницу между двумя итераторами `reverse_iterator`, которые ссылаются на элементы в одном контейнере.|  
|[iterator\_type](../Topic/reverse_iterator::iterator_type.md)|Тип, предоставляющий базовый итератор для итератора `reverse_iterator`.|  
|[указатель](../Topic/reverse_iterator::pointer.md)|Тип, содержащий указатель на элемент, к которому обращается итератор `reverse_iterator`.|  
|[reference](../Topic/reverse_iterator::reference.md)|Тип, содержащий ссылку на элемент, к которому обращается итератор `reverse_iterator`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[base](../Topic/reverse_iterator::base.md)|Восстановление базового итератора из соответствующего итератора `reverse_iterator`.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator\*](../Topic/reverse_iterator::operator*.md)|Возвращение элемента, к которому обращается `reverse_iterator`.|  
|[operator\+](../Topic/reverse_iterator::operator+.md)|Добавление смещения к итератору и возврат нового итератора `reverse_iterator`, который обращается к вставленному элементу в новой позиции смещения.|  
|[operator\+\+](../Topic/reverse_iterator::operator++.md)|Увеличение `reverse_iterator` до следующего элемента.|  
|[operator\+\=](../Topic/reverse_iterator::operator+=.md)|Добавление заданного смещения из итератора `reverse_iterator`.|  
|[operator\-](../Topic/reverse_iterator::operator-.md)|Вычитание смещения из итератора `reverse_iterator` с возвратом итератора `reverse_iterator`, который обращается к элементу в позиции со сдвигом.|  
|[operator\-\-](../Topic/reverse_iterator::operator--.md)|Уменьшение `reverse_iterator` до предыдущего элемента.|  
|[operator\-\=](../Topic/reverse_iterator::operator-=.md)|Вычитание заданного смещения из итератора `reverse_iterator`.|  
|[operator\-\>](../Topic/reverse_iterator::operator-%3E.md)|Возвращение указателя на элемент, к которому обращается `reverse_iterator`.|  
|[operator&#91;&#93;](../Topic/reverse_iterator::operator.md)|Возврат ссылки на смещение элемента из элемента, к которому обращается `reverse_iterator`, на указанное число позиций.|  
  
## Требования  
 **Заголовок:** \<iterator\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<iterator\>](../standard-library/iterator.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)