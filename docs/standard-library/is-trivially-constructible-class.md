---
title: "Класс is_trivially_constructible | Microsoft Docs"
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
  - "is_trivially_constructible"
  - "std.is_trivially_constructible"
  - "std::is_trivially_constructible"
  - "type_traits/std::is_trivially_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_constructible"
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Класс is_trivially_constructible
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли тип тривиально конструируемый при использовании указанным типам аргументов.  
  
## Синтаксис  
  
```  
template <class T, class... Args>  
    struct is_trivially_constructible;  
```  
  
#### Параметры  
 `T`  
 Запрашиваемый тип.  
  
 `Args`  
 Типы аргументов для сопоставления в конструктор `T`.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если тип `T` является тривиально конструируемый с помощью типов аргументов в `Args`, в противном случае — значение false. Тип `T` является тривиально конструируемый Если определение переменной `T t(std::declval<Args>()...);` имеет правильный формат и известные вызов не нетривиального операций. Оба `T` и все типы в `Args` должны быть полными типами `void`, или массивы неизвестной границей.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)