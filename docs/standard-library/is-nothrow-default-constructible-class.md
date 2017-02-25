---
title: "Класс is_nothrow_default_constructible | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_nothrow_default_constructible"
  - "std.is_nothrow_default_constructible"
  - "std::is_nothrow_default_constructible"
  - "type_traits/std::is_nothrow_default_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_default_constructible"
ms.assetid: c576fcc9-5be1-43aa-b93a-64d3f1848887
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# Класс is_nothrow_default_constructible
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, есть ли у типа невызывающий конструктор по умолчанию.  
  
## Синтаксис  
  
```  
template<class Ty>  
    struct is_nothrow_default_constructible;  
```  
  
#### Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если тип `Ty` имеет конструктор nothrow по умолчанию, в противном случае — значение false.  Экземпляр предиката типа эквивалентен `is_nothrow_constructible<Ty>`.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)