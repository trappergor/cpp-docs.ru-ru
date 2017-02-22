---
title: "&lt;sstream&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<sstream>"
  - "std::<sstream>"
  - "<sstream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sstream - заголовок"
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# &lt;sstream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет несколько шаблонных классов, поддерживающие операции iostreams с последовательностями, хранящиеся в выбранном объекте массива.  Такие последовательности легко преобразуются в строку и обратно объектов класса шаблона [basic\_string](../standard-library/basic-string-class.md).  
  
## Синтаксис  
  
```  
namespace std {  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_stringbuf;  
typedef basic_stringbuf<char> stringbuf;  
typedef basic_stringbuf<wchar_t> wstringbuf;  
  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_istringstream;  
typedef basic_istringstream<char> istringstream;  
typedef basic_istringstream<wchar_t> wistringstream;  
  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_ostringstream;  
typedef basic_ostringstream<char> ostringstream;  
typedef basic_ostringstream<wchar_t> wostringstream;  
  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_stringstream;  
typedef basic_stringstream<char> stringstream;  
typedef basic_stringstream<wchar_t> wstringstream;  
  
        // TEMPLATE FUNCTIONS  
template<class CharType, class Traits, class Allocator>  
    void swap(  
        basic_stringbuf<CharType, Traits, Allocator>& _Left,  
        basic_stringbuf<CharType, Traits, Allocator>& _Right  
    );   
template<class CharType, class Traits, class Allocator>  
    void swap(  
        basic_istringstream<CharType, Traits, Allocator>& _Left,  
        basic_istringstream<CharType, Traits, Allocator>& _Right  
    );  
template<class CharType, class Traits, class Allocator>  
    void swap(  
        basic_ostringstream<CharType, Traits, Allocator>& _Left,  
        basic_ostringstream<CharType, Traits, Allocator>& _Right  
    );  
template<class CharType, class Traits, class Allocator>  
    void swap (  
        basic_stringstream<CharType, Traits, Allocator>& _Left,  
        basic_stringstream<CharType, Traits, Allocator>& _Right  
    );  
}  // namespace std  
  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`_Left`|Используйте в `sstream` объект.|  
|`_Right`|Используйте в `sstream` объект.|  
  
## Заметки  
 Объекты типа `char *` могут использовать функции в [\<strstream\>](../standard-library/strstream.md) для выполнения.  Однако `<strstream>` стали сопоставления и использовать `<sstream>` ободрено.  
  
### Определения типов  
  
|||  
|-|-|  
|[istringstream](../Topic/istringstream.md)|Создает тип `basic_istringstream` специализированное для параметра шаблона `char`.|  
|[ostringstream](../Topic/ostringstream.md)|Создает тип `basic_ostringstream` специализированное для параметра шаблона `char`.|  
|[stringbuf](../Topic/stringbuf.md)|Создает тип `basic_stringbuf` специализированное для параметра шаблона `char`.|  
|[stringstream](../Topic/stringstream.md)|Создает тип `basic_stringstream` специализированное для параметра шаблона `char`.|  
|[wistringstream](../Topic/wistringstream.md)|Создает тип `basic_istringstream` специализированное для параметра шаблона `wchar_t`.|  
|[wostringstream](../Topic/wostringstream.md)|Создает тип `basic_ostringstream` специализированное для параметра шаблона `wchar_t`.|  
|[wstringbuf](../Topic/wstringbuf.md)|Создает тип `basic_stringbuf` специализированное для параметра шаблона `wchar_t`.|  
|[wstringstream](../Topic/wstringstream.md)|Создает тип `basic_stringstream` специализированное для параметра шаблона `wchar_t`.|  
  
### Манипуляторов  
  
|||  
|-|-|  
|[буфер обмена](../Topic/%3Csstream%3E%20swap.md)|Меняет местами значения 2 между объектами `sstream`.|  
  
### Классы  
  
|||  
|-|-|  
|[basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)|Описывает буфер потока, элементы управления и элементов типа **Elem**, в котором характеристики символа определяемые классом **Tr**, входящие и исходящие последовательности элементов, хранящихся в объекте массива.|  
|[basic\_istringstream](../standard-library/basic-istringstream-class.md)|Описывает объект, извлечение элементов управления и элементов кодированных объектов из буфера потока класса [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<**Elem**, **Tr**, `Alloc`\>, используя элементы типа **Elem**, в котором характеристики символа определяемые классом **Tr**, элементы которого выделяются распределителем класса `Alloc`.|  
|[basic\_ostringstream](../standard-library/basic-ostringstream-class.md)|Описывает объект, вставка элементов управления и элементов кодированных объектов в буфер потока класса [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<**Elem**, **Tr**, `Alloc`\>, используя элементы типа **Elem**, в котором характеристики символа определяемые классом **Tr**, элементы которого выделяются распределителем класса `Alloc`.|  
|[basic\_stringstream](../standard-library/basic-stringstream-class.md)|Описание объекта, что элементы управления вставки и извлечение элементов и кодированных объектов с использованием буфер потока класса [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<**Elem**, **Tr**, `Alloc`\>, используя элементы типа **Elem**, в котором характеристики символа определяемые классом **Tr**, элементы которого выделяются распределителем класса `Alloc`.|  
  
## Требования  
  
-   **Заголовок:**\<sstream\>  
  
-   **Пространство имен:** std  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)