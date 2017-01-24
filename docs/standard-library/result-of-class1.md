---
title: "Класс result_of | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "result_of"
  - "std.result_of"
  - "std::result_of"
  - "type_traits/std::result_of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "result_of"
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс result_of
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет возвращаемый тип вызываемой типа, который принимает указанным типам аргументов.  
  
## Синтаксис  
  
```  
template <class Fn, class... ArgTypes>  
    struct result_of<Fn(ArgTypes...)>;  
```  
  
#### Параметры  
 `Fn`  
 Тип вызываемой для запроса.  
  
 `ArgTypes`  
 Типы список аргументов для вызываемых тип запроса.  
  
## Заметки  
 Используйте этот шаблон, чтобы определить во время компиляции тип результата `Fn`\(`ArgTypes`\), где `Fn` является типом вызываемой вызывается со списком аргументов типов в `ArgTypes`.`type` Имен членов класса шаблона тип результата `decltype(INVOKE(declval<Fn>(), declval<ArgTypes>()...))` Если неоцененные выражение `INVOKE(declval<Fn>(), declval<ArgTypes>()...)` имеет правильный формат. В противном случае — класс шаблона не имеет члена `type`. Тип `Fn` и все типы в пакете параметра `ArgTypes` должны быть полными типами `void`, или массивы неизвестной границей.  
  
## Требования  
 **Заголовок:** \<type\_traits\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<type\_traits\>](../standard-library/type-traits.md)