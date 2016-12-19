---
title: "Класс basic_istringstream | Microsoft Docs"
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
  - "std::basic_istringstream"
  - "sstream/std::basic_istringstream"
  - "basic_istringstream"
  - "std.basic_istringstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_istringstream - класс"
ms.assetid: 1d5bb4b5-793d-4833-98e5-14676c451915
caps.latest.revision: 19
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс basic_istringstream
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает объект, управляющий извлечением элементов и закодированных объектов из буфера класса [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<**Elem**, **Tr**, `Alloc`\>.  
  
## Синтаксис  
  
```  
  
        template <  
   class Elem,   
   class Tr = char_traits<Elem>,   
   class Alloc = allocator<Elem>   
>  
   class basic_istringstream : public basic_istream<Elem, Tr>  
```  
  
#### Параметры  
 `Alloc`  
 Класс распределителя.  
  
 `Elem`  
 Тип основного элемента строки.  
  
 *Tr*  
 Признаки символа, соответствующие основному элементу строки.  
  
## Заметки  
 Класс шаблона описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<**Elem**, **Tr**, `Alloc`\> с элементами типа **Elem**. Их признаки символов определяются классом **Tr**, а элементы выделяются распределителем класса `Alloc`.  Объект сохраняет объект класса basic\_stringbuf\<**Elem**, **Tr**, `Alloc`\>.  
  
### Конструкторы  
  
|||  
|-|-|  
|[basic\_istringstream](../Topic/basic_istringstream::basic_istringstream.md)|Создает объект типа `basic_istringstream`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/basic_istringstream::allocator_type.md)|Этот тип является синонимом для параметра шаблона `Alloc`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[rdbuf](../Topic/basic_istringstream::rdbuf.md)|Возвращает адрес буфера сохраненного потока типа `pointer` в [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<`Elem`, `Tr`, `Alloc`\>.|  
|[str](../Topic/basic_istringstream::str.md)|Задает или получает текст в буфере строк без изменения позиции записи.|  
|[swap](../Topic/basic_istringstream::swap.md)|Меняет местами значения в этом объекте `basic_istringstream` и значения предоставленного объекта.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator \=](../Topic/basic_istringstream::operator=.md)|Назначает значения этому объекту `basic_istringstream` из параметра объекта.|  
  
## Требования  
 **Заголовок:** \<sstream\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)