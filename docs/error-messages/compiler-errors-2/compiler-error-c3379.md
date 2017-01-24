---
title: "Ошибка компилятора C3379 | Microsoft Docs"
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
  - "C3379"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3379"
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3379
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс": вложенный класс не может содержать спецификатор уровня доступа сборки как часть объявления  
  
 Ключевые слова [public](../../cpp/public-cpp.md) и [private](../Topic/private%20\(C++\).md), применяемые к управляемым типа, например к классам или структурам, определяют возможность предоставления класса посредством метаданных сборки.  Ключевые слова `public` и `private` не могут применяться к вложенному классу, наследующему уровень доступа сборки содержащего класса.  
  
 При использовании с параметром [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) ключевые слова `ref` и `value` указывают на то, что класс является управляемым \(см. раздел [Классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md)\).  
  
 Следующий пример приводит к возникновению ошибки C3379:  
  
```  
// C3379a.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class A {  
public:  
   static int i = 9;  
  
   public ref class BA {   // C3379  
   // try the following line instead  
   // ref class BA {  
   public:  
      static int ii = 8;  
   };  
};  
  
int main() {  
  
   A^ myA = gcnew A;  
   Console::WriteLine(myA->i);  
  
   A::BA^ myBA = gcnew A::BA;  
   Console::WriteLine(myBA->ii);  
}  
```  
  
 Следующий пример приводит к возникновению ошибки C3379:  
  
```  
// C3379b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
public __gc class A {  
public:  
   static int i = 9;  
  
   public __gc class BA {   // C3379  
   // try the following line instead  
   // __gc class BA {  
   public:  
      static int ii = 8;  
   };  
};  
  
int main() {  
  
   A *myA = new A;  
   Console::WriteLine(myA->i);  
  
   A::BA *myBA = new A::BA;  
   Console::WriteLine(myBA->ii);  
}  
```