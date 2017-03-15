---
title: "Оператор выражений | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "операторы выражений"
  - "операторы, выражение"
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Оператор выражений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Операторы выражений обеспечивают вычисление выражений.  В результате выполнения оператора выражения ни передачи управления, ни итерации не происходит.  
  
 Синтаксис оператора выражения простой:  
  
## Синтаксис  
  
```  
[expression ] ;  
```  
  
## Заметки  
 Вычисление всех выражений в операторе выражения и учет всех побочных эффектов осуществляются до выполнения следующего оператора.  Самые распространенные операторы выражений — присваивания и вызовы функций.  Поскольку выражение является необязательным, отдельная точка с запятой считается пустым оператором выражения и называется оператором [NULL](../Topic/Null%20Statement.md).  
  
## См. также  
 [Общие сведения об операторах в C\+\+](../cpp/overview-of-cpp-statements.md)