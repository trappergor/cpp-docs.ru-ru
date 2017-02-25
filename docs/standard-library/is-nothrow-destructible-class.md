---
title: "Класс is_nothrow_destructible | Microsoft Docs"
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
  - "is_nothrow_destructible"
  - "std.is_nothrow_destructible"
  - "std::is_nothrow_destructible"
  - "type_traits/std::is_nothrow_destructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_destructible"
ms.assetid: 0bbd8a28-e312-4d72-bd28-aac027f974d3
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Класс is_nothrow_destructible
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли тип разрушаемых и деструктор известен компилятор не будет выдавать.  
  
## Синтаксис  
  
```  
template <class T>  
    struct is_nothrow_destructible;  
```  
  
#### Параметры  
 `T`  
 Запрашиваемый тип.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если тип `T` является типом разрушаемых и деструктор известен компилятор не будет выдавать. В противном случае — значение false.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)