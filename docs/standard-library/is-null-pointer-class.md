---
title: "Класс is_null_pointer | Microsoft Docs"
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
  - "is_null_pointer"
  - "std.is_null_pointer"
  - "std::is_null_pointer"
  - "type_traits/std::is_null_pointer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_null_pointer"
ms.assetid: f3b3601b-f162-4803-a6e9-dabf5c3876cc
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Класс is_null_pointer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли тип std::nullptr\_t.  
  
## Синтаксис  
  
```  
template<class T>  
    struct is_null_pointer;  
```  
  
#### Параметры  
 `T`  
 Запрашиваемый тип.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если тип `T` — `std::nullptr_t`, в противном случае — значение false.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)