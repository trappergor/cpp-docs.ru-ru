---
title: "Ошибка компилятора C3417 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3417"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3417"
ms.assetid: 3e7869ea-8948-42fb-ba30-6ccafe499c35
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C3417
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"член": типы значений не могут содержать определенные пользователем специальные функции члена  
  
 Типы значений не могут содержать функции, такие как конструктор экземпляров по умолчанию, деконструктор или конструктор копий.  
  
 Следующий пример приводит к возникновению ошибки C3517:  
  
```  
// C3417.cpp  
// compile with: /clr /c  
value class VC {  
   VC(){}   // C3417  
  
   // OK  
   static VC(){}  
   VC(int i){}  
};  
```