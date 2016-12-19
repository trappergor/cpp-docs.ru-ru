---
title: "Класс is_literal_type | Microsoft Docs"
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
  - "is_literal_type"
  - "std.is_literal_type"
  - "std::is_literal_type"
  - "type_traits/std::is_literal_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_literal_type"
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
caps.latest.revision: 12
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс is_literal_type
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли тип можно использовать в качестве `constexpr` переменной или отправки, используемые или возвращенных `constexpr` функции.  
  
## Синтаксис  
  
```  
template <class T>  
    struct is_literal_type;  
```  
  
#### Параметры  
 `T`  
 Запрашиваемый тип.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если тип `T` — *типа литерала*, в противном случае — значение false. Тип литерала является либо `void`, скалярный тип, ссылочный тип, массив типа литерала или литерал типа. Литерал типа является типом класса, который содержит тривиальный деструктор, имеет составной тип или имеет по крайней мере один не move, отличных от копирования `constexpr` конструктор и всех его базовых классов и членов нестатических данных являются неизменяемые типы литералов. Хотя тип литерала всегда типа литерала, концепции литерал типа включает в себя все, что компилятор может вычислить в качестве `constexpr` во время компиляции.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)