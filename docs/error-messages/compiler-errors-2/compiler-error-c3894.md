---
title: "Ошибка компилятора C3894 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3894"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3894"
ms.assetid: 6d5ac903-1dea-431d-8e3a-cebca4342983
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C3894
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"var": статический элемент статических данных initonly в виде l\-значения можно использовать только в конструкторе класса для класса "класс"  
  
 Статические члены данных [initonly](../../dotnet/initonly-cpp-cli.md) можно использовать только как l\-значения в точке их объявления, либо в статическом конструкторе.  
  
 Члены данных экземпляра \(не статического\) initonly могут быть использованы только как l\-значения в точке их объявления, либо в конструкторах экземпляров \(не статических\).  
  
 Следующий пример приводит к возникновению ошибки C3894:  
  
```  
// C3894.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly static int data_var = 0;  
  
public:  
   // class constructor  
   static Y1() {  
      data_var = 99;   // OK  
      System::Console::WriteLine("in static constructor");  
   }  
  
   // not the class constructor  
   Y1(int i) {  
      data_var = i;   // C3894  
   }  
  
   static void Test() {}  
  
};  
  
int main() {  
   Y1::data_var = 88;   // C3894  
   int i = Y1::data_var;  
   Y1 ^ MyY1 = gcnew Y1(99);  
   Y1::Test();  
}  
```