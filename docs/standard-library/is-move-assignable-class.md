---
title: "Класс is_move_assignable | Microsoft Docs"
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
  - "is_move_assignable"
  - "std.is_move_assignable"
  - "std::is_move_assignable"
  - "type_traits/std::is_move_assignable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_move_assignable"
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс is_move_assignable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет тип можно переместить назначенного.  
  
## Синтаксис  
  
```  
template<class T>  
    struct is_move_assignable;  
```  
  
#### Параметры  
 `T`  
 Запрашиваемый тип.  
  
## Заметки  
 Тип является присваиваемым перемещения, если ссылка rvalue на тип могут быть назначены ссылка на тип. Предикат типа эквивалентен `is_assignable<T&, T&&>`. Переместите назначаемых типов включают член, на который скалярных типов и типов классов, содержащих компилятором или определяемые пользователем операторы присваивания.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)