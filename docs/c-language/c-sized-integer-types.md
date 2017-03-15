---
title: "Целочисленные типы размеров C | Microsoft Docs"
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
  - "целочисленные типы размеров"
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Целочисленные типы размеров C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 В Microsoft C поддерживаются целочисленные типы с указанием размера.  Это позволяет объявлять 8\-, 16\-, 32\- и 64\-разрядные целочисленные переменные при помощи спецификатора типа \_\_int*n* \(где *n* означает размер целочисленной переменной в битах\).  Таким образом, *n* может иметь значение 8, 16, 32 или 64.  В следующем примере объявляется по одной переменной каждого из 4 целочисленных типов с указанием размера:  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 Первые три целочисленных типа с указанием размера аналогичны типам данных ANSI с таким же размером. Они могут использоваться для написания переносимого кода, который одинаково работает на разных платформах.  Обратите внимание, что тип данных \_\_int8 синонимичен типу char, тип \_\_int16 — типу short, а тип \_\_int32 — типу int.  Тип \_\_int64 не имеет соответствующего эквивалента в ANSI.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Хранение базовых типов](../c-language/storage-of-basic-types.md)