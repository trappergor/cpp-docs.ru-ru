---
title: "Побитовые операции с числами со знаком | Microsoft Docs"
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
  - "поразрядные операции"
  - "поразрядные операции со знаком"
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Побитовые операции с числами со знаком
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.3** Результаты выполнения побитовых операций над знаковыми целочисленными значениями  
  
 Побитовые операции над знаковыми целочисленными значениями работают так же, как и над беззнаковыми.  Например, значение `–16 & 99` можно представить в двоичном виде следующим образом:  
  
```  
  11111111 11110000  
& 00000000 01100011  
  _________________  
  00000000 01100000  
```  
  
 Результат выполнения побитовой операции И будет равен 96.  
  
## См. также  
 [Целые числа](../Topic/Integers.md)