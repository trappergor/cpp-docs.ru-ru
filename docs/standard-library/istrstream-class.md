---
title: "Класс istrstream | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "istrstream"
  - "std::istrstream"
  - "std.istrstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istrstream - класс"
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# Класс istrstream
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [strstreambuf](../standard-library/strstreambuf-class.md).  
  
## Синтаксис  
  
```  
  
class istrstream : public istream  
  
```  
  
## Заметки  
 Объект сохраняет объект класса `strstreambuf`.  
  
> [!NOTE]
>  Этот класс устарел. Рассмотрите возможность использования [istringstream](../Topic/istringstream.md) или [wistringstream](../Topic/wistringstream.md) вместо.  
  
### Конструкторы  
  
|||  
|-|-|  
|[istrstream](../Topic/istrstream::istrstream.md)|Создает объект типа `istrstream`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[rdbuf](../Topic/istrstream::rdbuf.md)|Возвращает указатель на объект `strstreambuf`, связанный с потоком.|  
|[str](../Topic/istrstream::str.md)|Вызывает [freeze](../Topic/strstreambuf::freeze.md), затем возвращает указатель на начало управляемой последовательности.|  
  
## Требования  
 **Заголовок:** \< strstream \>  
  
 **Пространство имен:** std  
  
## См. также  
 [istream](../Topic/istream.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)