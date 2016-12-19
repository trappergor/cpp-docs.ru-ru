---
title: "Класс is_trivially_copy_constructible | Microsoft Docs"
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
  - "is_trivially_copy_constructible"
  - "std.is_trivially_copy_constructible"
  - "std::is_trivially_copy_constructible"
  - "type_traits/std::is_trivially_copy_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_copy_constructible"
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
caps.latest.revision: 24
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс is_trivially_copy_constructible
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, если тип содержит тривиальный конструктор копии.  
  
## Синтаксис  
  
```  
template<class T>  
    struct is_trivially_copy_constructible;  
```  
  
#### Параметры  
 `T`  
 Запрашиваемый тип.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если тип `T` является классом, имеющим тривиальный конструктор копирования, в противном случае — значение false.  
  
 Конструктор копии для класса `T` является тривиальным, если он неявно объявлен, класс `T` не имеет виртуальных функций или виртуальных базовых классов, все прямые базы класса `T` имеют конструкторы копий тривиальный, классы всех нестатических данных члены типа класса имеют тривиальные копирования конструкторы и классы всех нестатических данных элементов массива типов класса имеют тривиальные копирования конструкторы.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)