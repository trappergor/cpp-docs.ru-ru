---
title: "Класс is_trivially_copyable | Microsoft Docs"
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
  - "is_trivially_copyable"
  - "std.is_trivially_copyable"
  - "std::is_trivially_copyable"
  - "type_traits/std::is_trivially_copyable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_copyable"
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Класс is_trivially_copyable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли тип типом доступна для простого копирования.  
  
## Синтаксис  
  
```  
template<class T>  
    struct is_trivially_copyable;  
```  
  
#### Параметры  
 `T`  
 Запрашиваемый тип.  
  
## Заметки  
 Экземпляр предиката типа содержит значение true, если тип `T` является тривиально копируемыми типа, в противном случае — значение false. Доступна для простого копирования типы не имеют нетривиального копирования, операции перемещения и деструкторы. Как правило операция копирования считается тривиальным, если он может быть реализован как побитовое копирование. Встроенные типы и массивы типов доступна для простого копирования можно просто копировать.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)