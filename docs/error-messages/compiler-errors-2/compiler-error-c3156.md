---
title: "Ошибка компилятора C3156 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3156"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3156"
ms.assetid: 1876da78-b94e-4af7-9795-28f72b209b3e
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C3156
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

class: нельзя иметь локальное определение управляемого типа или типа WinRT  
  
 Функция не может содержать определение или объявление управляемого класса, структуры или интерфейса либо класса, структуры или интерфейса WinRT.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3156.  
  
```  
// C3156.cpp  
// compile with: /clr /c  
void f() {  
   ref class X {};   // C3156  
   ref class Y;   // C3156  
}  
```  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3156.  
  
```  
// C3156_b.cpp  
// compile with: /clr:oldSyntax /c  
void f() {  
   __gc class X {};   // C3156  
   __gc class Y;   // C3156  
}  
```