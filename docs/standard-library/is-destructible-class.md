---
title: "Класс is_destructible | Microsoft Docs"
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
  - "is_destructible"
  - "std.is_destructible"
  - "std::is_destructible"
  - "type_traits/std::is_destructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_destructible"
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# Класс is_destructible
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, можно ли уничтожить тип.  
  
## Синтаксис  
  
```  
template <class T>  
    struct is_destructible;  
```  
  
#### Параметры  
 `T`  
 Запрашиваемый тип.  
  
## Заметки  
 Экземпляр предиката типа имеет значение true, если тип `T` можно уничтожить, в противном случае — значение false. К типам, которые можно уничтожить, относятся ссылочные типы, типы объектов и типы, для которых при типе `U`, равном `remove_all_extents_t<T>`, невычисленный операнд `std::declval<U&>.~U()` имеет правильный формат. Другие типы, включая незавершенные, `void` и типы функций, не являются типами, которые можно уничтожить.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)