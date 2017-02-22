---
title: "Функции без прототипа | Microsoft Docs"
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
ms.assetid: 34200b8c-5b52-4f0d-aff8-9f70d82868ed
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Функции без прототипа
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для функций без прототипа вызывающий объект передает целые числа в виде значений типа Integer, а значения с плавающей запятой — в виде чисел двойной точности.  \(Только для значений с плавающей запятой\) Если вызываемый объект предполагает наличие значения в регистре операций с целыми числами, в регистрах операций с целыми числами и числами с плавающей запятой одновременно будут содержаться значения с плавающей запятой.  
  
```  
func1();  
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7  
   func1(2, 1.0, 7);  
}  
```  
  
## См. также  
 [Соглашение о вызовах](../build/calling-convention.md)