---
title: "Структура treat_as_floating_point | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "chrono/std::chrono::treat_as_floating_point"
dev_langs: 
  - "C++"
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Структура treat_as_floating_point
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет, является ли `Rep` можно считать с плавающей запятой.  
  
## Синтаксис  
  
```  
template<class Rep>  
struct treat_as_floating_point : is_floating_point<Rep>;  
```  
  
## Заметки  
 `Rep` можно считать с плавающей запятой, только если специализация `treat_as_floating_point<Rep>` остается в [true\_type](../Topic/true_type%20Typedef.md).  Класс шаблона можно настроить для пользовательского типа.  
  
## Требования  
 **Заголовок:**  chrono  
  
 **Пространство имен:**  std::chrono  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)