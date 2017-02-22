---
title: "Класс is_trivially_move_constructible | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_trivially_move_constructible"
  - "std.is_trivially_move_constructible"
  - "std::is_trivially_move_constructible"
  - "type_traits/std::is_trivially_move_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_move_constructible"
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Класс is_trivially_move_constructible
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, есть ли у типа тривиальный конструктор перемещения.  
  
## Синтаксис  
  
```  
template<class Ty>  
    struct is_trivially_move_constructible;  
```  
  
#### Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если тип `Ty` является классом, имеющим тривиальный конструктор перемещения, в противном случае — значение false.  
  
 Конструктор перемещения для класса `Ty` является тривиальным, если:  
  
 он неявно объявлен;  
  
 его типы параметров эквивалентны типам неявного объявления;  
  
 класс `Ty` не имеет виртуальных функций;  
  
 класс `Ty` не имеет виртуальных баз;  
  
 класс не содержит изменчивых нестатических элементов данных;  
  
 все прямые базы класса `Ty` имеют тривиальные конструкторы перемещения;  
  
 классы всех нестатических элементов данных типа класса имеют тривиальные конструкторы перемещения;  
  
 классы всех нестатических элементов данных массива типов класса имеют тривиальные конструкторы перемещения.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)