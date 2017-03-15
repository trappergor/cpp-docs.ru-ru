---
title: "Класс allocator&lt;void&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "memory/std::allocator<void>"
  - "std::allocator<void>"
  - "std.allocator<void>"
  - "allocator<void>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator<void> - класс"
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# Класс allocator&lt;void&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Специализация распределителя класса шаблона для ввода `void`, определяя типы, иметь в этом контексте.  
  
## Синтаксис  
  
```  
template<>  
   class allocator<void> {  
   typedef void *pointer;  
   typedef const void *const_pointer;  
   typedef void value_type;  
   template<class Other>  
      struct rebind;  
   allocator( );  
   allocator(  
      const allocator<void>&  
   );  
   template<class Other>  
      allocator(  
         const allocator<Other>&  
      );  
   template<class Other>  
      allocator<void>& operator=(  
         const allocator<Other>&  
      );  
   };  
```  
  
## Заметки  
 Класс явно специализирует шаблонный класс [allocator](../standard-library/allocator-class.md) для типа *void*. Его конструкторов и оператор присваивания ведут себя так же, как для класса шаблона, но он определяет только следующие типы:  
  
-   [const\_pointer](../Topic/allocator::const_pointer.md).  
  
-   [указатель](../Topic/allocator::pointer.md).  
  
-   [value\_type](../Topic/allocator::value_type.md).  
  
-   [rebind](../Topic/allocator::rebind.md), вложенный класс шаблона.  
  
## Требования  
 **Header:** \<memory\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)