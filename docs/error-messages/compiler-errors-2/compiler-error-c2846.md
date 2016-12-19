---
title: "Ошибка компилятора C2846 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2846"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2846"
ms.assetid: bc090ec2-5410-4112-9ec6-261325374375
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2846
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

конструктор: интерфейс не может иметь конструктор  
  
 Visual C\+\+ [интерфейс](../Topic/__interface.md) не может иметь конструктор.  
  
 Следующий пример приводит к возникновению ошибки C2846:  
  
```  
// C2846.cpp  
// compile with: /c  
__interface C {  
   C();   // C2846 constructor not allowed in an interface  
};  
```