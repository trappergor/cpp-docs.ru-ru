---
title: "Класс strstream | Microsoft Docs"
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
  - "std::strstream"
  - "strstream"
  - "std.strstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strstream - класс"
ms.assetid: 63f3be31-9e36-42b1-9715-a474a5997e2a
caps.latest.revision: 21
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс strstream
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает объект, управляющий вставкой и извлечением элементов и закодированных объектов с помощью буфера потока класса [strstreambuf](../standard-library/strstreambuf-class.md).  
  
## Синтаксис  
  
```  
  
class strstream : public iostream  
  
```  
  
## Заметки  
 Объект сохраняет объект класса `strstreambuf`.  
  
> [!NOTE]
>  Этот класс устарел.  Вместо него рекомендуется использовать [stringstream](../Topic/stringstream.md) или [wstringstream](../Topic/wstringstream.md).  
  
### Конструкторы  
  
|||  
|-|-|  
|[strstream](../Topic/strstream::strstream.md)|Создает объект типа `strstream`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[freeze](../Topic/strstream::freeze.md)|Делает буфер потока недоступным для операций с буфером потока.|  
|[pcount](../Topic/strstream::pcount.md)|Возвращает число элементов, записанных в управляемую последовательность.|  
|[rdbuf](../Topic/strstream::rdbuf.md)|Возвращает указатель на объект `strstreambuf`, связанный с потоком.|  
|[str](../Topic/strstream::str.md)|Вызывает [freeze](../Topic/strstreambuf::freeze.md), затем возвращает указатель на начало управляемой последовательности.|  
  
## Требования  
 **Заголовок:** \< strstream \>  
  
 **Пространство имен:** std  
  
## См. также  
 [iostream](../Topic/iostream.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)