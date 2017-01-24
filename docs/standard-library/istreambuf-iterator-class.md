---
title: "Класс istreambuf_iterator | Microsoft Docs"
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
  - "istreambuf_iterator"
  - "std.istreambuf_iterator"
  - "std::istreambuf_iterator"
  - "streambuf/std::istreambuf_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istreambuf_iterator - класс"
ms.assetid: 39002da2-61a6-48a5-9d0c-5df8271f6038
caps.latest.revision: 19
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс istreambuf_iterator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Istreambuf\_iterator шаблонного класса описывает объект итератора ввода, который извлекает элементы символов из буфера потока ввода, к которому он получает доступ через хранимый им объект, относящийся к типу указателя на `basic_streambuf`\<**CharType**, **Признаки**\>.  
  
## Синтаксис  
  
```  
  
      template <   
   class CharType  
   class Traits = char_traits<CharType>  
>  
class istreambuf_iterator  
: public iterator<input_iterator_tag, CharType, typename Traits::off_type, CharType *, CharType&>  
```  
  
#### Параметры  
 `CharType`  
 Тип, представляющий тип символа для istreambuf\_iterator.  
  
 `Traits`  
 Тип, представляющий тип символа для istreambuf\_iterator.  Этот аргумент является необязательным, и значением по умолчанию является `char_traits`\<*CharType\>.*  
  
## Заметки  
 Класс istreambuf\_iterator должен удовлетворять требованиям для итератора ввода.  
  
 После создания или увеличения объекта класса istreambuf\_iterator с помощью сохраненного указателя, не содержащего null, объект фактически пытается извлечь и сохранить объект типа **CharType** из соответствующего входного потока.  Однако извлечение может быть отложено, пока не будет фактически удалена ссылка объекта или он не будет скопирован.  Если извлечение завершается ошибкой, этот объект фактически заменяет сохраненный указатель указателем null, тем самым создавая индикатор конца последовательности.  
  
### Конструкторы  
  
|||  
|-|-|  
|[istreambuf\_iterator](../Topic/istreambuf_iterator::istreambuf_iterator.md)|Создает объект `istreambuf_iterator`, инициализируемый для чтения символов из входного потока.|  
  
### Определения типов  
  
|||  
|-|-|  
|[char\_type](../Topic/istreambuf_iterator::char_type.md)|Тип, обеспечивающий тип символа для `ostreambuf_iterator`.|  
|[int\_type](../Topic/istreambuf_iterator::int_type.md)|Тип, предоставляющий целочисленный тип для `istreambuf_iterator`.|  
|[istream\_type](../Topic/istreambuf_iterator::istream_type.md)|Тип, обеспечивающий тип потока для `istream_iterator`.|  
|[streambuf\_type](../Topic/istreambuf_iterator::streambuf_type.md)|Тип, обеспечивающий тип потока для `istreambuf_iterator`.|  
|[traits\_type](../Topic/istream_iterator::traits_type.md)|Тип, обеспечивающий тип признаков символа для `istream_iterator`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[equal](../Topic/istreambuf_iterator::equal.md)|Тесты на равенство между двумя итераторами буфера входного потока.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator\*](../Topic/istreambuf_iterator::operator*.md)|Оператор удаления ссылки возвращает следующий символ в потоке.|  
|[operator\+\+](../Topic/istreambuf_iterator::operator++.md)|Либо возвращает следующий символ из входного потока, либо копирует объект перед его увеличением и возвращает копию.|  
|[operator\-\>](../Topic/istreambuf_iterator::operator-%3E.md)|Возвращает значение члена при наличии.|  
  
## Требования  
 **Заголовок:** \<iterator\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Структура iterator](../Topic/iterator%20Struct.md)   
 [\<iterator\>](../standard-library/iterator.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)