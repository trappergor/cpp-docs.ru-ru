---
title: "Ошибка компилятора C2691 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2691"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2691"
ms.assetid: 6925f8f3-ea60-4909-91e6-b781492c645d
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Ошибка компилятора C2691
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип данных": управляемый массив или массив WinRT не может содержать элементы этого типа  
  
 Тип управляемого элемента массива или элемента массива WinRT может быть типом значения или ссылочным типом.  
  
 Следующий пример приводит к возникновению ошибки C2691:  
  
```  
// C2691a.cpp  
// compile with: /clr  
class A {};  
  
int main() {  
   array<A>^ a1 = gcnew array<A>(20);   // C2691  
   array<int>^ a2 = gcnew array<int>(20);   // value type OK  
}  
```  
  
 Следующий пример приводит к возникновению ошибки C2691:  
  
```  
// C2691b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
int main() {  
   int * a1 __gc[];   // C2691  
   int * a1 = new int [20];   // OK  
}  
```  
  
 Ошибка C2691 также может возникнуть при попытке определить неравномерный массив с помощью управляемых расширений для C\+\+.  Неравномерные массивы поддерживаются в текущем синтаксисе \(см. раздел [Массивы](../../windows/arrays-cpp-component-extensions.md)\).  
  
 Следующий пример приводит к возникновению ошибки C2691:  
  
```  
// C2691c.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
int main() {  
   Int32 myJaggedArray[][] = new Int32 [50][];   // C2691  
}  
```