---
title: "Класс slice_array | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "slice_array"
  - "valarray/std::slice_array"
  - "std.slice_array"
  - "std::slice_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "slice_array - класс"
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# Класс slice_array
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Внутренний вспомогательный класс шаблона, который поддерживает объекты метода, обеспечивая операций между массивами подмножества, методом valarray.  
  
## Синтаксис  
  
```  
template<class Type>  
   class slice_array : public slice {  
public:  
   typedef Type value_type;  
   void operator=(  
      const valarray<Type>& x  
   ) const;  
   void operator=(  
      const Type& x  
   ) const;  
   void operator*=(  
      const valarray<Type>& x  
   ) const;  
   void operator/=(  
      const valarray<Type>& x  
   ) const;  
   void operator%=(  
      const valarray<Type>& x  
   ) const;  
   void operator+=(  
      const valarray<Type>& x  
   ) const;  
   void operator-=(  
      const valarray<Type>& x  
   ) const;  
   void operator^=(  
      const valarray<Type>& x  
   ) const;  
   void operator&=(  
      const valarray<Type>& x  
   ) const;  
   void operator|=(  
      const valarray<Type>& x  
   ) const;  
   void operator<<=(  
      const valarray<Type>& x  
   ) const;  
   void operator>>=(  
      const valarray<Type>& x  
   ) const;  
// The rest is private or implementation defined  
}  
```  
  
## Заметки  
 Класс описывает объект, который содержит ссылку на объект класса [valarray](../standard-library/valarray-class.md)**\<Type\>** вместе с объектом класса [метод](../Topic/slice%20Class.md), который описывает последовательность элементов, чтобы выделить из объекта **valarray\<Type\>**.  
  
 Класс шаблона создается косвенно valarray некоторыми операциями и не может использоваться непосредственно в программе.  Внутренний вспомогательный класс шаблона, который используется оператор индекса метода:  
  
 ::\<`operator[]` \>`slice_array`\<**Тип**`valarray`**Тип**\(`slice`\).  
  
 При создании объекта **slice\_array\<Type\>** только путем написания формы выражение [va sl &#91;&#93;](../Topic/valarray::operator.md), для метода **sl** valarray **va**.  Функции\-члены класса slice\_array затем аналогично поведению соответствующий сигнатуры функции, определенные для **valarray\<Type\>**, за исключением того, что только последовательность выбранных элементов относится.  Последовательность контролируемая slice\_array 3 определяется параметрами конструктора метода, индекс первого элемента в методе, количества элементов и расстояния между элементами.  Slice\_array вырезать из valarray объявленного **va**\[ **va**`slice`\(2, 5, 3\)\] выделяет элементы с индексами 2, 5, 8, 11 и 14 из **va**.  Индексы должны быть допустимы для процедуры было допустимым.  
  
## Пример  
 См. пример для [slice::slice](../Topic/slice::slice.md) пример способы объявления и использования slice\_array.  
  
## Требования  
 **Заголовок:**\<valarray\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)