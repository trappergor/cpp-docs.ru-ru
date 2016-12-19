---
title: "Ошибка компилятора C3374 | Microsoft Docs"
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
  - "C3374"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3374"
ms.assetid: 41431299-bd20-47d4-a0c8-1334dd79018b
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3374
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

невозможно взять адрес 'функции' без создания экземпляра делегата  
  
 Адрес функции был взят в контексте, отличном от создания экземпляра делегата.  
  
 Следующий пример приводит к возникновению ошибки C3374:  
  
```  
// C3374.cpp  
// compile with: /clr  
public delegate void MyDel(int i);  
  
ref class A {  
public:  
   void func1(int i) {  
      System::Console::WriteLine("in func1 {0}", i);  
   }  
};  
  
int main() {  
   &A::func1;   // C3374  
  
   // OK  
   A ^ a = gcnew A;  
   MyDel ^ StaticDelInst = gcnew MyDel(a, &A::func1);  
}  
```  
  
## См. также  
 [Практическое руководство. Определение и использование делегатов](../Topic/How%20to:%20Define%20and%20Use%20Delegates%20\(C++-CLI\).md)