---
title: "Ошибка компилятора C2533 | Microsoft Docs"
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
  - "C2533"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2533"
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2533
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

identifier: конструкторы не разрешены для возвращаемого типа  
  
 Конструктор класса не может иметь возвращаемый тип \(даже тип `void`\).  
  
 Типичной причиной возникновения этой ошибки является отсутствие точки с запятой между концом определения класса и первой реализацией конструктора.  Компилятор считает класс определением возвращаемого типа для функции конструктора класса и вызывает ошибку C2533.  
  
 В следующем примере показано возникновение ошибки C2533 и приводятся сведения по ее устранению.  
  
```  
// C2533.cpp  
// compile with: /c  
class X {  
public:  
   X();     
};  
  
int X::X() {}   // C2533 - constructor return type not allowed  
X::X() {}   // OK - fix by using no return type  
```