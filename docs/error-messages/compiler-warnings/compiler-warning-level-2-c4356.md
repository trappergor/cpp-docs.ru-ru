---
title: "Предупреждение компилятора (уровень 2) C4356 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4356"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4356"
ms.assetid: 3af3defe-de33-43b6-bd6c-2c2e09e34f3f
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Предупреждение компилятора (уровень 2) C4356
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"член" : статический член данных не может инициализироваться через производный класс  
  
 Инициализация статического члена данных задана неправильно.  Компилятор принял эту инициализацию.  
  
 Это критическое изменение в компиляторе Visual C\+\+ .NET 2003.  
  
 В коде, который функционирует одинаково во всех версиях Visual C\+\+, следует инициализировать член через базовый класс.  
  
 Используйте директиву pragma [warning](../../preprocessor/warning.md) для подавления этого предупреждения.  
  
 Следующий пример приводит к возникновению ошибки C4356:  
  
```  
// C4356.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
  
template <class T>  
class C {  
   static int n;  
};  
  
class D : C<int> {};  
  
int D::n = 0; // C4356  
// try the following line instead  
// int C<int>::n = 0;  
  
class A {  
public:  
   static int n;  
};  
  
class B : public A {};  
  
int B::n = 10;   // C4356  
// try the following line instead  
// int A::n = 99;  
  
int main() {  
   using namespace std;  
   cout << B::n << endl;  
}  
```