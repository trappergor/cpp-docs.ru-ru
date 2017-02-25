---
title: "Ошибка компилятора C2845 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2845"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2845"
ms.assetid: 31b28ee9-978f-403b-94d8-dbaacd24cce0
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Ошибка компилятора C2845
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"оператор": арифметические операции с указателями не допускаются для данного типа  
  
 Невозможно увеличить указатель на управляемый класс.  
  
 **Управляемые расширения для C\+\+**  
  
 Указатель на класс [\_\_gc](../Topic/__gc.md) увеличивать нельзя.  Кроме того, строковые операторы допустимы только при использовании параметра **\/clr** \(но не с параметром **\/clr:oldSyntax**\).  
  
 Следующий пример приводит к возникновению ошибки C2845:  
  
```  
// C2845b.cpp  
// compile with: /clr:oldSyntax  
using namespace System;  
__gc class X {};  
  
int main() {  
   X *pX = new X;  
   pX++;   // C2845  
  
   String * a = new String("abc");  
   String * b = new String("def");  
   Console::WriteLine(a + b);   // C2845 not with /clr:oldSyntax  
}  
```