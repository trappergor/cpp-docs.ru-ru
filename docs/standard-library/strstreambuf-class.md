---
title: "Класс strstreambuf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.strstreambuf"
  - "strstreambuf"
  - "std::strstreambuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strstreambuf - класс"
ms.assetid: b040b8ea-0669-4eba-8908-6a9cc159c54b
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# Класс strstreambuf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает буфер потока, который управляет передачей элементов из последовательности элементов, содержащейся в объекте массива `char`, и в эту последовательность.  
  
## Синтаксис  
  
```  
  
class strstreambuf : public streambuf  
  
```  
  
## Заметки  
 В зависимости от способа создания объекта он выделяется, расширяется и освобождается при необходимости для обеспечения соответствия изменениям в последовательности.  
  
 Объект класса `strstreambuf` хранит несколько битов сведений о режиме в качестве своего режима `strstreambuf`. Эти биты определяют следующие сведения об управляемой последовательности:  
  
-   она выделена, и ее со временем нужно освободить;  
  
-   ее можно изменять;  
  
-   она расширяется за счет перераспределения хранилища;  
  
-   она заморожена, поэтому ее необходимо разморозить до уничтожения или освобождения \(если он выделен\) объекта элементом, отличным от объекта.  
  
 Замороженную управляемую последовательность невозможно изменить или расширить независимо от состояния этих отдельных битов режима.  
  
 Объект также хранит указатели на две функции, которые управляют выделением `strstreambuf`. Если это пустые указатели, объект использует собственный метод выделения и освобождения памяти для управляемой последовательности.  
  
> [!NOTE]
>  Этот класс устарел. Рассмотрите возможность использования [stringbuf](../Topic/stringbuf.md) или [wstringbuf](../Topic/wstringbuf.md) вместо.  
  
### Конструкторы  
  
|||  
|-|-|  
|[strstreambuf](../Topic/strstreambuf::strstreambuf.md)|Создает объект типа `strstreambuf`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[freeze](../Topic/strstreambuf::freeze.md)|Делает буфер потока недоступным для операций с буфером потока.|  
|[переполнение](../Topic/strstreambuf::overflow.md)|Защищенная виртуальная функция, которая может вызываться при вставке нового символа в полный буфер.|  
|[pbackfail](../Topic/strstreambuf::pbackfail.md)|Защищенная виртуальная функция\-член, которая пытается поместить элемент обратно во входной поток, а затем делает его текущим \(на него указывает следующий указатель\).|  
|[pcount](../Topic/strstreambuf::pcount.md)|Возвращает число элементов, записанных в управляемую последовательность.|  
|[seekoff](../Topic/strstreambuf::seekoff.md)|Защищенная виртуальная функция\-член, которая пытается изменить текущие положения управляемых потоков.|  
|[seekpos](../Topic/strstreambuf::seekpos.md)|Защищенная виртуальная функция\-член, которая пытается изменить текущие положения управляемых потоков.|  
|[str](../Topic/strstreambuf::str.md)|Вызывает [freeze](../Topic/strstreambuf::freeze.md), затем возвращает указатель на начало управляемой последовательности.|  
|[underflow](../Topic/strstreambuf::underflow.md)|Защищенная виртуальная функция для извлечения текущего элемента из входного потока.|  
  
## Требования  
 **Заголовок:** \< strstream \>  
  
 **Пространство имен:** std  
  
## См. также  
 [streambuf](../Topic/streambuf.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)