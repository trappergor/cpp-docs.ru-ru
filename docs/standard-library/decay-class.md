---
title: "Класс decay | Microsoft Docs"
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
  - "decay"
  - "std.tr1.decay"
  - "std::tr1::decay"
  - "std.decay"
  - "std::decay"
  - "type_traits/std::decay"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "decay - класс [TR1]"
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс decay
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает тип, как передаются по значению. Создает не ссылочный тип, не являющимся константным, долговременного, либо указатель на тип функции или тип массива.  
  
## Синтаксис  
  
```  
template<class T>  
    struct decay;  
  
template<class T> using decay_t = typename decay<T>::type;  
```  
  
#### Параметры  
 `T`  
 Тип для изменения.  
  
## Заметки  
 Используйте шаблон затухания для создания результирующего типа, как если бы тип был передан в качестве аргумента. Typedef члена класса шаблона `type` содержит измененный тип, который определяется следующим образом:  
  
-   Тип `U` определяется как `remove_reference<T>::type`.  
  
-   Если `is_array<U>::value` имеет значение true, измененного типа `type` — `remove_extent<U>::type *`.  
  
-   В противном случае, если `is_function<U>::value` имеет значение true, измененного типа `type` — `add_pointer<U>::type`.  
  
-   В противном случае — измененного типа `type` — `remove_cv<U>::type`.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)