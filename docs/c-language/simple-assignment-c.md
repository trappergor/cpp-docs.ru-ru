---
title: "Простое назначение (C) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "операторы присваивания [C++], простые"
  - "преобразование типов данных [C++], простое присваивание"
  - "знак равенства"
  - "операторы [C], простое присваивание"
  - "оператор простого присваивания"
  - "преобразование типов [С++], простое присваивание"
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Простое назначение (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Оператор простого присваивания присваивает значение правого операнда левому операнду.  Значения правого операнда преобразуется в тип выражения присваивания и заменяет значение, хранящееся в объекте, определяемом левым операндом.  Применяются правила преобразования для присваивания \(см. раздел [Преобразования при присваивании](../c-language/assignment-conversions.md)\).  
  
```  
double x;  
int y;  
  
x = y;  
```  
  
 В этом примере значение переменной `y` преобразуется в тип **double** и присваивается переменной `x`.  
  
## См. также  
 [Операторы назначения в C](../c-language/c-assignment-operators.md)