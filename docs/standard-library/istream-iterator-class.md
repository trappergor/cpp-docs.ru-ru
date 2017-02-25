---
title: "Класс istream_iterator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "iterator/std::istream_iterator"
  - "std.istream_iterator"
  - "std::istream_iterator"
  - "istream_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istream_iterator - класс"
ms.assetid: fb52a8cd-7f71-48d1-b73e-4b064e2a8d16
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# Класс istream_iterator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает объект итератора ввода.  Извлекает объекты класса `Type` из входного потока, доступ к которому получает через сохраненный объект, относящийся к типу `pointer`, на `basic_istream`\<`CharType`, `Traits`\>.  
  
## Синтаксис  
  
```  
template<class Type,  
    class CharType = char,  
    class Traits = char_traits<CharType>,  
    class Distance = ptrdiff_t,  
> class istream_iterator  
 : public iterator<  
        input_iterator_tag,  
        Type,   
        Distance,   
        const Type *,  
        const Type&  
    >;  
```  
  
#### Параметры  
 `Type`  
 Тип объекта, который необходимо извлечь из потока ввода.  
  
 `CharType`  
 Тип, представляющий шрифт символа для `istream_iterator`.  Этот аргумент является необязательным, и значением по умолчанию является `char`.  
  
 `Traits`  
 Тип, представляющий шрифт символа для `istream_iterator`.  Этот аргумент является необязательным, и значением по умолчанию является `char_traits`\<`CharType`\>.  
  
 `Distance`  
 Тип целого числа со знаком, представляющий тип отличия для `istream_iterator`.  Этот аргумент является необязательным, и значением по умолчанию является `ptrdiff_t`.  
  
 После создания или увеличения объекта класса istream\_iterator с помощью сохраненного указателя, не содержащего null, объект фактически пытается извлечь и сохранить объект типа `Type` из соответствующего входного потока.  Если извлечение завершается ошибкой, этот объект фактически заменяет сохраненный указатель указателем null, тем самым создавая индикатор конца последовательности.  
  
### Конструкторы  
  
|||  
|-|-|  
|[istream\_iterator](../Topic/istream_iterator::istream_iterator.md)|Создает итератор конца потока в качестве итератора `istream_iterator` по умолчанию или итератор `istream_iterator`, инициализированный в тип потока итератора, из которого он считывается.|  
  
### Определения типов  
  
|||  
|-|-|  
|[char\_type](../Topic/istream_iterator::char_type.md)|Тип, обеспечивающий тип символа для `istream_iterator`.|  
|[istream\_type](../Topic/istream_iterator::istream_type.md)|Тип, обеспечивающий тип потока для `istream_iterator`.|  
|[traits\_type](../Topic/istream_iterator::traits_type.md)|Тип, обеспечивающий тип признаков символа для `istream_iterator`.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator\*](../Topic/istream_iterator::operator*.md)|Оператор удаления ссылки возвращает сохраненный объект типа `Type`, к которому обращается `istream_iterator`.|  
|[operator\-\>](../Topic/istream_iterator::operator-%3E.md)|Возвращает значение члена при наличии.|  
|[operator\+\+](../Topic/istream_iterator::operator++.md)|Либо извлекает увеличенный объект из входного потока, либо копирует объект перед его увеличением и возвращает копию.|  
  
## Требования  
 **Заголовок:** \<iterator\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Структура input\_iterator\_tag](../standard-library/input-iterator-tag-struct.md)   
 [Структура iterator](../Topic/iterator%20Struct.md)   
 [\<iterator\>](../standard-library/iterator.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)