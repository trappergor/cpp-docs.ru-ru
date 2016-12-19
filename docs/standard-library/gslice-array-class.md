---
title: "Класс gslice_array | Microsoft Docs"
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
  - "std::gslice_array"
  - "gslice_array"
  - "valarray/std::gslice_array"
  - "std.gslice_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gslice_array - класс"
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс gslice_array
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Внутренний вспомогательный класс шаблона, который поддерживает общие объекты метода, обеспечивая операций между массивами подмножества, используемым методом valarray.  
  
## Синтаксис  
  
```  
template<class Type>  
   class gslice_array : public gsplice {  
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
 Класс описывает объект, который содержит ссылку на объект **va** класса [valarray](../standard-library/valarray-class.md)**\<Type\>** вместе с объектом **gs** класса [gslice](../Topic/gslice%20Class.md), который описывает последовательность элементов, чтобы выделить из объекта **valarray\<Type\>**.  
  
 При создании объекта **gslice\_array\<Type\>** только путем написания выражений формы [va &#91;gs&#93;](../Topic/valarray::operator.md).  Функции\-члены класса gslice\_array затем аналогично поведению соответствующий сигнатуры функции, определенные для **valarray\<Type\>**, за исключением того, что только последовательность выбранных элементов относится.  
  
 Класс шаблона создается косвенно valarray некоторыми операциями и не может использоваться непосредственно в программе.  Внутренний вспомогательный класс шаблона используется вместо оператора индекса метода:  
  
 ::\<`operator[]` \>`gslice_array`\<**Тип**\>`valarray`**Тип**\(**const gslice&**\).  
  
 При создании объекта **gslice\_array\<Type\>** только путем написания выражение в форме **va\[gsl\]** для метода **gsl** valarray **va**.  Функции\-члены класса gslice\_array затем аналогично поведению соответствующий сигнатуры функции, определенные для **valarray\<Type\>**, за исключением того, что только последовательность выбранных элементов относится.  Последовательность контролируемая gslice\_array 3 определяется параметрами конструктора метода, индекс первого элемента в первом методе, количество элементов в каждом методе и расстояния между элементами в каждом методе.  
  
 В следующем примере:  
  
```  
const size_t lv[] = {2, 3};  
const size_t dv[] = {7, 2};  
const valarray<size_t> len(lv, 2), str(dv, 2);  
// va[gslice(3, len, str)] selects elements with  
//   indices 3, 5, 7, 10, 12, 14  
```  
  
 Индексы должны быть допустимы для процедуры было допустимым.  
  
## Пример  
 См. пример для [gslice::gslice](../Topic/gslice::gslice.md) пример способы объявления и использования slice\_array.  
  
## Требования  
 **Заголовок:**\<valarray\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)