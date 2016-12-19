---
title: "Класс basic_ostringstream | Microsoft Docs"
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
  - "basic_ostringstream"
  - "std.basic_ostringstream"
  - "sstream/std::basic_ostringstream"
  - "std::basic_ostringstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ostringstream - класс"
ms.assetid: aea699f7-350f-432a-acca-adbae7b483fb
caps.latest.revision: 19
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс basic_ostringstream
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<**Elem**, **Tr**, `Alloc`\>.  
  
## Синтаксис  
  
```  
  
        template <  
   class Elem,   
   class Tr = char_traits<Elem>,   
   class Alloc = allocator<Elem>   
>  
   class basic_ostringstream : public basic_ostream<Elem, Tr>  
```  
  
#### Параметры  
 `Alloc`  
 Класс распределителя.  
  
 `Elem`  
 Тип основного элемента строки.  
  
 *Tr*  
 Признаки символа, соответствующие основному элементу строки.  
  
## Заметки  
 Этот класс описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока с элементами типа **Elem**. Их признаки символов определяются классом **Tr**, а элементы выделяются распределителем класса `Alloc`.  Объект сохраняет объект класса basic\_stringbuf\<**Elem**, **Tr**, `Alloc`\>.  
  
### Конструкторы  
  
|||  
|-|-|  
|[basic\_ostringstream](../Topic/basic_ostringstream::basic_ostringstream.md)|Создает объект типа `basic_ostringstream`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/basic_ostringstream::allocator_type.md)|Этот тип является синонимом для параметра шаблона `Alloc`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[rdbuf](../Topic/basic_ostringstream::rdbuf.md)|Возвращает адрес буфера сохраненного потока типа `pointer` в [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<`Elem`, `Tr`, `Alloc`\>.|  
|[str](../Topic/basic_ostringstream::str.md)|Задает или получает текст в буфере строк без изменения позиции записи.|  
  
## Требования  
 **Заголовок:** \<sstream\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)