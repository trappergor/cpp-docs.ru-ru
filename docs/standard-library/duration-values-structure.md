---
title: "Структура duration_values | Microsoft Docs"
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
  - "chrono/std::chrono::duration_values"
dev_langs: 
  - "C++"
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
caps.latest.revision: 13
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Структура duration_values
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Содержит определенные значения для параметра `Rep` шаблона [длительность](../standard-library/duration-class.md).  
  
## Синтаксис  
  
```  
template<class Rep>  
   struct duration_values;  
```  
  
## Члены  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод duration\_values::max](../Topic/duration_values::max%20Method.md)|Статический.  Указывает верхний предел для значения типа `Rep`.|  
|[Метод duration\_values::min](../Topic/duration_values::min%20Method.md)|Статический.  Определяет нижний предел для значения типа `Rep`.|  
|[Метод duration\_values::zero](../Topic/duration_values::zero%20Method.md)|Статический.  Возвращает `Rep(0)`.|  
  
## Требования  
 **Заголовок:**  chrono  
  
 **Пространство имен:**  std::chrono  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)