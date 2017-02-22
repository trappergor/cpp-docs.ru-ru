---
title: "Класс basic_iostream | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "istream/std::basic_iostream"
  - "std.basic_iostream"
  - "basic_iostream"
  - "std::basic_iostream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_iostream - класс"
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# Класс basic_iostream
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс потока, поддерживающий ввод и вывод.  
  
## Синтаксис  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_iostream : public basic_istream<Elem, Tr>,  
        public basic_ostream<Elem, Tr>  
{  
public:  
    explicit basic_iostream(basic_streambuf<Elem, Tr> *_Strbuf);  
    virtual ~basic_iostream();  
};  
```  
  
## Заметки  
 Этот класс шаблона описывает объект, управляющий вставками с помощью базового класса [basic\_ostream](../Topic/basic_ostream%20Class.md)\<`Elem`, `Tr`\> и извлечениями с помощью базового класса [basic\_istream](../Topic/basic_istream%20Class.md)\<`Elem`, `Tr`\>.  У этих двух объектов общий виртуальный базовый класс [basic\_ios](../Topic/basic_ios%20Class.md)\<`Elem`, `Tr`\>.  Они также управляют общим буфером потока с элементами типа `Elem`, признаки символов которых определяются классом `Tr`.  Конструктор инициализирует базовые классы с помощью `basic_istream`\(**strbuf**\) и `basic_ostream`\(**strbuf**\).  
  
### Конструкторы  
  
|||  
|-|-|  
|[basic\_iostream](../Topic/basic_iostream::basic_iostream.md)|Создание объекта `basic_iostream`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[swap](../Topic/basic_iostream::swap.md)|Меняет местами содержимое предоставленного объекта `basic_iostream` на содержимое этого объекта.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator \=](../Topic/basic_iostream::operator=.md)|Присваивает значение указанного объекта `basic_iostream` этому объекту.  Это присваивание перемещением, включающее `rvalue`, которое не оставляет копию.|  
  
## Требования  
 **Заголовок:** \<istream\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)