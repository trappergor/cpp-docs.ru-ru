---
title: "Класс basic_stringstream | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.basic_stringstream"
  - "basic_stringstream"
  - "std::basic_stringstream"
  - "sstream/std::basic_stringstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_stringstream - класс"
ms.assetid: 49629814-ca37-45c5-931b-4ff894e6ebd2
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс basic_stringstream
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает объект, управляющий вставкой и извлечением элементов и закодированных объектов с помощью буфера потока класса [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<**Elem**, **Tr**, `Alloc`\>.  
  
## Синтаксис  
  
```  
  
        template <  
   class Elem,   
   class Tr = char_traits<Elem>,   
   class Alloc = allocator<Elem>   
>  
   class basic_stringstream : public basic_iostream<Elem, Tr>  
```  
  
#### Параметры  
 `Alloc`  
 Класс распределителя.  
  
 `Elem`  
 Тип основного элемента строки.  
  
 *Tr*  
 Признаки символа, соответствующие основному элементу строки.  
  
## Заметки  
 Класс шаблона описывает объект, управляющий извлечением и вставкой элементов и закодированных объектов с помощью буфера потока класса [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<**Elem**, **Tr**, `Alloc`\> с элементами типа **Elem**. Их признаки символов определяются классом **Tr**, а элементы выделяются распределителем класса `Alloc`.  Объект сохраняет объект класса basic\_stringbuf\<**Elem**, **Tr**, `Alloc`\>.  
  
### Конструкторы  
  
|||  
|-|-|  
|[basic\_stringstream](../Topic/basic_stringstream::basic_stringstream.md)|Создает объект типа `basic_stringstream`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/basic_stringstream::allocator_type.md)|Этот тип является синонимом для параметра шаблона `Alloc`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[rdbuf](../Topic/basic_stringstream::rdbuf.md)|Возвращает адрес буфера сохраненного потока типа `pointer` в [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<`Elem`, `Tr`, `Alloc`\>.|  
|[str](../Topic/basic_stringstream::str.md)|Задает или получает текст в буфере строк без изменения позиции записи.|  
  
## Требования  
 **Заголовок:** \<sstream\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)