---
title: "Класс is_nothrow_copy_constructible | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_nothrow_copy_constructible"
  - "std.is_nothrow_copy_constructible"
  - "std::is_nothrow_copy_constructible"
  - "type_traits/std::is_nothrow_copy_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_copy_constructible"
ms.assetid: f13a0bea-63b1-492a-9a45-d445df35c282
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# Класс is_nothrow_copy_constructible
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, обладает ли тип конструктором копии  [nothrow](../Topic/nothrow%20\(C++\).md).  
  
## Синтаксис  
  
```  
template<class Ty>  
    struct is_nothrow_copy_constructible;  
```  
  
#### Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## Заметки  
 Экземпляр предиката типа имеет значение true, если тип `Ty` имеет конструктор копии nothrow, в противном случае — значение false.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)