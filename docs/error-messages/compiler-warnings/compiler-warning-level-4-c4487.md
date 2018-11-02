---
title: Предупреждение компилятора (уровень 4) C4487
ms.date: 11/04/2016
f1_keywords:
- C4487
helpviewer_keywords:
- C4487
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
ms.openlocfilehash: 743069c0ed3103a2ed8d459def65083146b971e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497042"
---
# <a name="compiler-warning-level-4-c4487"></a>Предупреждение компилятора (уровень 4) C4487

«невиртуальному»: соответствует унаследованного невиртуальному методу «базового класса», но не помечен явно как «new»

Функция в производном классе имеет ту же сигнатуру, как функция невиртуальный базовый класс. C4487 напомнит о том, что функция производного класса не переопределяет функции базового класса. Явным образом пометить функция производного класса как `new` Чтобы устранить это предупреждение.

Дополнительные сведения см. в разделе [new (новый слот в vtable)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4487.

```
// C4487.cpp
// compile with: /W4 /clr
using namespace System;
public ref struct B {
   void f() { Console::WriteLine("in B::f"); }
   void g() { Console::WriteLine("in B::g"); }
};

public ref struct D : B {
   void f() { Console::WriteLine("in D::f"); }   // C4487
   void g() new { Console::WriteLine("in D::g"); }   // OK
};

int main() {
   B ^ a = gcnew D;
   // will call base class functions
   a->f();
   a->g();
}
```