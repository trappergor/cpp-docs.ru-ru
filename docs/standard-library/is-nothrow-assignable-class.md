---
title: "Класс is_nothrow_assignable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "is_nothrow_assignable"
  - "std.is_nothrow_assignable"
  - "std::is_nothrow_assignable"
  - "type_traits/std::is_nothrow_assignable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_assignable"
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Класс is_nothrow_assignable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли значение `From` типа могут быть назначены `To` не будет выдавать известен тип и назначения.  
  
## Синтаксис  
  
```  
template <class To, class From>   
    struct is_nothrow_assignable;  
```  
  
#### Параметры  
 Целевой тип  
 Тип объекта, который получает назначение.  
  
 От  
 Тип объекта, который предоставляет значение.  
  
## Заметки  
 Выражение `declval<To>() = declval<From>()` должен иметь правильный формат и должен быть известен компилятор не будет выдавать. Оба `From` и `To` должны быть полными типами `void`, или массивы неизвестной границей.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)