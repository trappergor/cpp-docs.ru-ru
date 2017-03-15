---
title: "Неустранимая ошибка C1103 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1103"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1103"
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Неустранимая ошибка C1103
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

неустранимая ошибка при импорте progid: "сообщение"  
  
 Компилятор обнаружил проблему при импорте библиотеки типов.  Например, нельзя указать библиотеку типов с помощью progid и в то же время указать `no_registry`.  
  
 Дополнительные сведения см. в разделе [Директива \#import](../Topic/%23import%20Directive%20\(C++\).md).  
  
 Следующий пример приводит к возникновению ошибки C1103:  
  
```  
// C1103.cpp #import "progid:a.b.id.1.5" no_registry auto_search   // C1103  
```