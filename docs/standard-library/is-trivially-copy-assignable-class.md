---
title: "Класс is_trivially_copy_assignable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_trivially_copy_assignable"
  - "std.is_trivially_copy_assignable"
  - "std::is_trivially_copy_assignable"
  - "type_traits/std::is_trivially_copy_assignable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_copy_assignable"
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# is_trivially_copy_assignable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, есть ли у типа тривиальный оператор присваивания копии.  
  
## Синтаксис  
  
```  
template<class Ty>  
    struct is_trivially_copy_constructible;  
```  
  
#### Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если тип `Ty` является классом, имеющим тривиальный оператор присваивания копии, в противном случае — значение false.  
  
 Конструктор присваивания для класса `Ty` является тривиальным, если:  
  
 он неявно предоставляется;  
  
 класс `Ty` не имеет виртуальных функций;  
  
 класс `Ty` не имеет виртуальных баз;  
  
 классы всех нестатических элементов данных типа класса имеют тривиальные операторы присваивания;  
  
 классы всех нестатических элементов данных массива типов класса имеют тривиальные операторы присваивания.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)