---
title: "Структура nothrow_t | Microsoft Docs"
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
  - "nothrow_t"
  - "std.nothrow_t"
  - "std::nothrow_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nothrow_t - класс"
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Структура nothrow_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Структура используется в качестве параметра функции для оператора new, чтобы указать, что функция должна возвращать указатель для оповещения сбой выделения, а не вызывает исключение.  
  
## Синтаксис  
  
```  
struct std::nothrow_t {};  
```  
  
## Заметки  
 Структура позволяет компилятору выбор правильной версии конструктора.  [nothrow](../Topic/nothrow%20\(%3Cnew%3E\).md) является синонимом типа объектов `std::nothrow_t`.  
  
## Пример  
 См. в разделах [оператор new](../Topic/operator%20new%20\(%3Cnew%3E\).md) и [оператор новый &#91;&#93;](../Topic/operator%20new\(%3Cnew%3E\).md) примеры `std::nothrow_t` используется в качестве параметра функции.  
  
## Требования  
 **Header:**\<new\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)