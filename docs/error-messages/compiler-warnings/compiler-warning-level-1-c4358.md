---
title: Предупреждение компилятора (уровень 1) C4358
ms.date: 11/04/2016
f1_keywords:
- C4358
helpviewer_keywords:
- C4358
ms.assetid: a9848f84-14b3-405e-81bf-ee3e91a51511
ms.openlocfilehash: 7722acbd1d2a7d9582dbf3e42d544ec3bd0d418c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187119"
---
# <a name="compiler-warning-level-1-c4358"></a>Предупреждение компилятора (уровень 1) C4358

"оператор": тип возвращаемого значения Объединенных делегатов не является "void"; Возвращаемое значение не определено

Два делегата были объединены, а возвращаемое значение не является void. Если два делегата с возвращаемыми значениями, отличными от void, объединяются, компилятор не сможет выполнить правильное присваивание, если используется возвращаемое значение делегата.

Следующий пример приводит к возникновению ошибки C4358:

```cpp
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
