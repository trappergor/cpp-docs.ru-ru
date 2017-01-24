---
title: "Ошибка компилятора C2577 | Microsoft Docs"
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
  - "C2577"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2577"
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2577
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"член": деструктор\/метод завершения не может иметь возвращаемый тип  
  
 Деструктор или метод завершения не может возвращать значение типа `void` или любого другого типа.  Удалите оператор `return` из определения деструктора.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2577.  
  
```  
// C2577.cpp  
// compile with: /c  
class A {  
public:  
   A() {}  
   ~A(){  
      return 0;   // C2577  
   }  
};  
```