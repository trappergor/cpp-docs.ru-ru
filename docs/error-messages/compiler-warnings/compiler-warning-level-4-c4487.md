---
title: Предупреждение компилятора (уровень 4) C4487
ms.date: 11/04/2016
f1_keywords:
- C4487
helpviewer_keywords:
- C4487
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
ms.openlocfilehash: b83b3b33727db300367156e10f902aaa6ff4bfdb
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990771"
---
# <a name="compiler-warning-level-4-c4487"></a>Предупреждение компилятора (уровень 4) C4487

"derived_class_function": соответствует унаследованному невиртуальному методу "base_class_function", но не помечен явно как "New"

Функция в производном классе имеет ту же сигнатуру, что и Невиртуальная функция базового класса. C4487 напоминает, что функция производного класса не переопределяет функцию базового класса. Чтобы устранить это предупреждение, явно пометьте функцию производного класса как `new`.

Дополнительные сведения см. в разделе [New (новый слот в таблице vtable)](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4487.

```cpp
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
