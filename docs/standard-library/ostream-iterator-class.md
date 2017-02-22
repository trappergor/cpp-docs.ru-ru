---
title: "Класс ostream_iterator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ostream_iterator"
  - "std.ostream_iterator"
  - "std::ostream_iterator"
  - "iterator/std::ostream_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ostream_iterator - класс"
ms.assetid: 24d842d3-9f45-4bf6-a697-62f5968f5a03
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# Класс ostream_iterator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ostream\_iterator класса шаблона описывает объект итератора вывода, который записывает идущие подряд элементы в поток вывода с помощью **оператора \<\<** извлечения.  
  
## Синтаксис  
  
```  
  
      template <  
   class Type   
   class CharType = char  
   class Traits = char_traits<CharType>  
>  
class ostream_iterator  
```  
  
#### Параметры  
 *Тип*  
 Тип объекта, который необходимо вставить в поток вывода.  
  
 `CharType`  
 Тип, представляющий шрифт символа для `ostream_iterator`.  Этот аргумент является необязательным, и значением по умолчанию является `char`*.*  
  
 `Traits`  
 Тип, представляющий шрифт символа для `ostream_iterator`.  Этот аргумент является необязательным, и значением по умолчанию является `char_traits`\<*CharType\>.*  
  
 Класс ostream\_iterator должен удовлетворять требованиям для итератора вывода.  Алгоритмы можно записывать непосредственно в потоки вывода с помощью `ostream_iterator`.  
  
### Конструкторы  
  
|||  
|-|-|  
|[ostream\_iterator](../Topic/ostream_iterator::ostream_iterator.md)|Создает `ostream_iterator`, инициализированный и разделенный для записи в поток вывода.|  
  
### Определения типов  
  
|||  
|-|-|  
|[char\_type](../Topic/ostream_iterator::char_type.md)|Тип, обеспечивающий тип символа для `ostream_iterator`.|  
|[ostream\_type](../Topic/ostream_iterator::ostream_type.md)|Тип, обеспечивающий тип потока для `ostream_iterator`.|  
|[traits\_type](../Topic/ostream_iterator::traits_type.md)|Тип, обеспечивающий тип признаков символа для `ostream_iterator`.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator\*](../Topic/ostream_iterator::operator*.md)|Оператор удаления ссылки, используемый для реализации выражения итератора вывода \*`i` \= `x`.|  
|[operator\+\+](../Topic/ostream_iterator::operator++.md)|Нефункциональный оператор инкремента, возвращающий `ostream_iterator`, обращающийся к тому же объекту, к которому он обращался до вызова операции.|  
|[operator\=](../Topic/ostream_iterator::operator=.md)|Оператор присваивания, используемый для реализации выражение итератора вывода \*`i` \= `x` для записи в поток вывода.|  
  
## Требования  
 **Заголовок:** \<iterator\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<iterator\>](../standard-library/iterator.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)