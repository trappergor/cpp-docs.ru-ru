---
title: "Класс ostreambuf_iterator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.ostreambuf_iterator"
  - "streambuf/std::ostreambuf_iterator"
  - "ostreambuf_iterator"
  - "std::ostreambuf_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ostreambuf_iterator - класс"
ms.assetid: dad1e624-2f45-4e94-8887-a885e95f9071
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# Класс ostreambuf_iterator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс шаблона ostreambuf\_iterator описывает объект итератора вывода, записывающий последующие элементы символов в поток вывода при **оператора\>\>** извлечения.  Итераторы `ostreambuf_iterator` отличаются от итераторов класса [ostream\_iterator](../standard-library/ostream-iterator-class.md) тем, чтоб обладают символами вместо универсального типа в типе объекта, вставляемого в поток вывода.  
  
## Синтаксис  
  
```  
  
      template <   
   class CharType = char  
   class Traits = char_traits<CharType>  
>  
```  
  
#### Параметры  
 `CharType`  
 Тип, представляющий тип символа для ostreambuf\_iterator.  Этот аргумент является необязательным, и значением по умолчанию является `char`*.*  
  
 `Traits`  
 Тип, представляющий тип символа для ostreambuf\_iterator.  Этот аргумент является необязательным, и значением по умолчанию является `char_traits`\<*CharType\>.*  
  
## Заметки  
 Класс ostreambuf\_iterator должен удовлетворять требованиям для итератора вывода.  Алгоритмы можно записывать непосредственно в потоки вывода с помощью `ostreambuf_iterator`.  Данный класс предоставляет итератор потока низкого уровня, обеспечивающий доступ к необработанному \(неотформатированному\) потоку ввода\-вывода в форме символов, а также возможность обхода буферизации и преобразования символов, связанных с итераторами потоков высокого уровня.  
  
### Конструкторы  
  
|||  
|-|-|  
|[ostreambuf\_iterator](../Topic/ostreambuf_iterator::ostreambuf_iterator.md)|Создает итератор `ostreambuf_iterator`, инициализированный для записи символов в поток вывода.|  
  
### Определения типов  
  
|||  
|-|-|  
|[char\_type](../Topic/ostreambuf_iterator::char_type.md)|Тип, обеспечивающий тип символа для `ostreambuf_iterator`.|  
|[ostream\_type](../Topic/ostreambuf_iterator::ostream_type.md)|Тип, обеспечивающий тип потока для `ostream_iterator`.|  
|[streambuf\_type](../Topic/ostreambuf_iterator::streambuf_type.md)|Тип, обеспечивающий тип потока для `ostreambuf_iterator`.|  
|[traits\_type](../Topic/ostreambuf_iterator::traits_type.md)|Тип, обеспечивающий тип признаков символа для `ostream_iterator`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[failed](../Topic/ostreambuf_iterator::failed.md)|Проверяет наличие ошибок вставки в буфер потока вывода.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator\*](../Topic/ostreambuf_iterator::operator*.md)|Оператор удаления ссылки, используемый для реализации выражения итератора вывода \*`i` \= `x`.|  
|[operator\+\+](../Topic/ostreambuf_iterator::operator++.md)|Нефункциональный оператор инкремента, возвращающий `ostreambuf_iterator`, обращающийся к тому же объекту, к которому он обращался до вызова операции.|  
|[operator\=](../Topic/ostreambuf_iterator::operator=.md)|Данный оператор вставляет символ в соответствующий буфер потока.|  
  
## Требования  
 **Заголовок:** \<iterator\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<iterator\>](../standard-library/iterator.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)