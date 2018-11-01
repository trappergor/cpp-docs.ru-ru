---
title: Предупреждение компилятора (уровень 1) C4358
ms.date: 11/04/2016
f1_keywords:
- C4358
helpviewer_keywords:
- C4358
ms.assetid: a9848f84-14b3-405e-81bf-ee3e91a51511
ms.openlocfilehash: aebac17a343efedf678b55f8940004c85a2db708
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637337"
---
# <a name="compiler-warning-level-1-c4358"></a>Предупреждение компилятора (уровень 1) C4358

«operator»: возвращаемый тип значения объединенных делегатов не «void»; Возвращаемое значение не определено

Объединить два делегата, и возвращаемое значение не является void. При объединении двух делегатов с возвращаемыми значениями отличный от void, компилятор не сможете выполнить присвоение в том случае, если используется возвращаемое значение делегата.

Следующий пример приводит к возникновению ошибки C4358:

```
// C4358.cpp
// compile with: /clr /W1
delegate int D();
delegate void E();

ref class X {
   int i;
public:
   X(int ii) : i(ii) {}
   int f() {
      return i;
   }
};

ref class Y {
   int i;
public:
   Y() {}
   void g() {}
};

int main() {
   D^ d = gcnew D(gcnew X(1), &X::f);
   D^ d2 = gcnew D(gcnew X(2), &X::f);

   d += d2;   // C4358
   int j = d();   // return value indeterminate

   E^ e = gcnew E(gcnew Y, &Y::g);
   E^ e2 = gcnew E(gcnew Y, &Y::g);
   e += e2;   // OK
}
```