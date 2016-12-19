---
title: "Ошибка компилятора C2663 | Microsoft Docs"
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
  - "C2663"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2663"
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2663
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"function" : числовые перегрузки не имеют действительных преобразований для указателя "this"  
  
 Компилятору не удается выполнить преобразование `this` в любую перегруженную версию функции\-члена.  
  
 Это ошибка может возникать в результате вызова функции\-члена, который не является членом `const` объекта `const`.  Возможные способы разрешения:  
  
1.  Удалите ключевое слово `const` из объявления объекта.  
  
2.  Добавьте `const` к одной из перегрузок функции\-члена.  
  
 Следующий пример приводит к возникновению ошибки C2663:  
  
```  
// C2663.cpp  
struct C {  
   void f() volatile {}  
   void f() {}  
};  
  
struct D {  
   void f() volatile;  
   void f() const {}  
};  
  
const C *pcc;  
const D *pcd;  
  
int main() {  
   pcc->f();    // C2663  
   pcd->f();    // OK  
}  
```