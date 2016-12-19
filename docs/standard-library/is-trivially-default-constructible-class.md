---
title: "Класс is_trivially_default_constructible | Microsoft Docs"
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
  - "is_trivially_default_constructible"
  - "std.is_trivially_default_constructible"
  - "std::is_trivially_default_constructible"
  - "type_traits/std::is_trivially_default_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_default_constructible"
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
caps.latest.revision: 17
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс is_trivially_default_constructible
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, есть ли у типа тривиальный конструктор по умолчанию.  
  
## Синтаксис  
  
```  
template<class Ty>  
    struct  is_trivially_default_constructible;  
```  
  
#### Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если тип `Ty` является классом, имеющим тривиальный конструктор, в противном случае — значение false.  
  
 Конструктор по умолчанию для класса `Ty` является тривиальным, если:  
  
-   он является конструктором по умолчанию, объявленным неявно;  
  
-   класс `Ty` не имеет виртуальных функций;  
  
-   класс `Ty` не имеет виртуальных баз;  
  
-   все прямые базы класса `Ty` имеют тривиальные конструкторы;  
  
-   классы всех нестатических элементов данных типа класса имеют тривиальные конструкторы;  
  
-   классы всех нестатических элементов данных массива типов класса имеют тривиальные конструкторы.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)