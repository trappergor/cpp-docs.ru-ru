---
title: "Класс underlying_type | Microsoft Docs"
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
  - "underlying_type"
  - "std.underlying_type"
  - "std::underlying_type"
  - "type_traits/std::underlying_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "underlying_type"
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Класс underlying_type
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает базового целочисленного типа для типа перечисления.  
  
## Синтаксис  
  
```  
template <class T>  
    struct underlying_type;  
```  
  
#### Параметры  
 `T`  
 Тип для изменения.  
  
## Заметки  
 `type` Typedef члена класса шаблона имена базового целочисленного типа `T`, когда `T` имеет тип перечисления, в противном случае будет не typedef члена `type`.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)