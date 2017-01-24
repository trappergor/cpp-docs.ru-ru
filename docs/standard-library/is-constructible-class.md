---
title: "Класс is_constructible | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_constructible"
  - "std.is_constructible"
  - "std::is_constructible"
  - "type_traits/std::is_constructible"
dev_langs: 
  - "C++"
  - "c++"
helpviewer_keywords: 
  - "is_constructible"
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
caps.latest.revision: 14
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс is_constructible
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли тип конструируемый при использовании указанным типам аргументов.  
  
## Синтаксис  
  
```  
template <class T, class... Args>  
    struct is_constructible;  
```  
  
#### Параметры  
 `T`  
 Запрашиваемый тип.  
  
 `Args`  
 Типы аргументов для сопоставления в конструктор `T`.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если тип `T` — создать с помощью типов аргументов в `Args`, в противном случае — значение false. Тип `T` создать при определении переменной `T t(std::declval<Args>()...);` имеет правильный формат. Оба `T` и все типы в `Args` должны быть полными типами `void`, или массивы неизвестной границей.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)