---
title: Ошибка компилятора C2247 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2247
dev_langs:
- C++
helpviewer_keywords:
- C2247
ms.assetid: 72efa03e-615e-4ef9-aede-0a98654b20fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed27398ea1f51ccc2ef0d3339446b422c7a503c0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172317"
---
# <a name="compiler-error-c2247"></a>Ошибка компилятора C2247
«Идентификатор» не доступен, поскольку «класс» использует «спецификатор» для наследования из «класс»  
  
 `identifier` наследуется от класса, объявленного с доступом к личным или защищенным.  
  
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
  
 Эта ошибка может также возникать в результате действий по обеспечению совместимости компилятора с Visual Studio .NET 2003: элементов управления доступом с защищенных членов. Защищенный элемент (n) может осуществляться только через функции-члена класса (B), который наследует от класса (A), членом которой он (n) является.  
  
 Для кода, который допустим в версиях Visual C++ в Visual Studio .NET и Visual Studio .NET 2003 объявите члена как дружественная типа. Также может использоваться открытое наследование.  
  
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
  
 C2247 также может возникать в результате действий по обеспечению совместимости компилятора с Visual Studio .NET 2003: закрытые базовые классы становятся недоступны. Класс (A) к типу закрытого базового класса (B) необходимо недоступен типу (C), использующий B в качестве базового класса.  
  
 Для кода, который допустим в версиях Visual C++ в Visual Studio .NET и Visual Studio .NET 2003 используйте оператор области действия.  
  
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