---
title: "Ошибка компилятора C2247 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2247"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2247"
ms.assetid: 72efa03e-615e-4ef9-aede-0a98654b20fd
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Ошибка компилятора C2247
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

нет доступа к "идентификатор", поскольку "класс" использует "спецификатор" для наследования из "класс"  
  
 Параметр `identifier` наследуется от класса, объявленного с уровнем доступа private или protected.  
  
 Следующий пример приводит к возникновению ошибки C2247:  
  
```  
// C2247.cpp  
class A {  
public:  
   int i;  
};  
class B : private A {};    // B inherits a private A  
class C : public B {} c;   // so even though C's B is public  
int j = c.i;               // C2247, i not accessible  
```  
  
 Эта ошибка также может возникать в результате выполнения действий по обеспечению совместимости элементов управления доступом с защищенными членами для Visual Studio .NET 2003.  Обращение к защищенному члену \(n\) может осуществляться только посредством функции\-члена класса \(B\), наследуемого от класса \(A\), членом которого является \(n\).  
  
 В коде, совместимом с версиями Visual C\+\+ для Visual Studio .NET 2003 и Visual Studio .NET, следует объявить член как дружественный для типа.  Также можно использовать механизм открытого наследования.  
  
```  
// C2247b.cpp  
// compile with: /c  
// C2247 expected  
class A {  
public:  
   void f();  
   int n;  
};  
  
class B: protected A {  
   // Uncomment the following line to resolve.  
   // friend void A::f();  
};  
  
void A::f() {  
   B b;  
   b.n;  
}  
```  
  
 Ошибка C2247 также может возникать в результате выполнения действий по обеспечению совместимости Visual Studio .NET 2003, в результате которых закрытые базовые классы становятся недоступны.  Класс \(A\), являющийся закрытым базовым классом для \(B\), должен быть недоступен типу \(C\), базовым для которого является класс B.  
  
 В коде, совместимом с версиями Visual C\+\+ для Visual Studio .NET 2003 и Visual Studio .NET, следует использовать оператор области видимости.  
  
```  
// C2247c.cpp  
// compile with: /c  
struct A {};  
  
struct B: private A {};  
  
struct C : B {  
   void f() {  
      A *p1 = (A*) this;   // C2247  
      // try the following line instead  
      // ::A *p2 = (::A*) this;  
   }  
};  
```