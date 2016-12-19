---
title: "Преобразования вызова функции | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "вызовы функций, преобразования типов аргументов"
  - "вызовы функций, преобразование"
  - "функции [C], преобразования аргументов"
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Преобразования вызова функции
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Тип преобразования, выполняемого над аргументами в вызове функции, зависит от того, имеется ли для вызываемой функции прототип функции \(предварительное объявление\) с объявленными типами аргументов.  
  
 Если прототип функции уже был указан и в нем объявлены типы аргументов, то компилятор выполняет проверку типа \(см. раздел [Функции](../Topic/Functions%20\(C\).md)\).  
  
 Если прототипа нет, то над аргументами в вызове функции выполняются только обычные арифметические преобразования.  Для каждого аргумента в вызове они выполняются отдельно.  Иными словами, значение **float** преобразуется в **double**; значение `char` или **short** — в `int`; а значение `unsigned char` или **unsigned short** — в `unsigned int`.  
  
## См. также  
 [Преобразования типов](../c-language/type-conversions-c.md)