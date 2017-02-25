---
title: "Класс is_nothrow_constructible | Microsoft Docs"
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
  - "is_nothrow_constructible"
  - "std.is_nothrow_constructible"
  - "std::is_nothrow_constructible"
  - "type_traits/std::is_nothrow_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_constructible"
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Класс is_nothrow_constructible
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли тип конструируемый, известны не будет выдавать при использовании указанным типам аргументов.  
  
## Синтаксис  
  
```  
template <class T, class... Args>  
    struct is_nothrow_constructible;  
```  
  
#### Параметры  
 `T`  
 Запрашиваемый тип.  
  
 `Args`  
 Типы аргументов для сопоставления в конструктор `T`.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если тип `T` — создать с помощью типов аргументов в `Args`, и конструктор известен, компилятор не будет выдавать; в противном случае — значение false. Тип `T` создать при определении переменной `T t(std::declval<Args>()...);` имеет правильный формат. Оба `T` и все типы в `Args` должны быть полными типами `void`, или массивы неизвестной границей.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)