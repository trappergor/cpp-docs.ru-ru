---
title: "Ошибка компилятора C2387 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2387"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2387"
ms.assetid: 6847b8e1-ffac-458d-ab88-0c92f72f2527
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2387
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": неоднозначный базовый класс  
  
 Компилятору не удалось однозначно разрешить вызов функции, поскольку функция существует в нескольких базовых классах.  
  
 Чтобы устранить данную ошибку, следует либо удалить один из базовых классов из наследования, либо явным образом квалифицировать вызов функции.  
  
 Следующий пример приводит к возникновению ошибки C2387:  
  
```  
// C2387.cpp  
namespace N1 {  
   struct B {  
      virtual void f() {  
      }  
   };  
}  
  
namespace N2 {  
   struct B {  
      virtual void f() {  
      }  
   };  
}  
  
struct D : N1::B, N2::B {  
   virtual void f() {  
      B::f();   // C2387  
      // try the following line instead  
      // N1::B::f();  
   }  
};  
  
int main() {  
   D aD;  
   aD.f();  
}  
```