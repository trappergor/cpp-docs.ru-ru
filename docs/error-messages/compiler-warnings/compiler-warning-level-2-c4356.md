---
title: Предупреждение компилятора (уровень 2) C4356
ms.date: 11/04/2016
f1_keywords:
- C4356
helpviewer_keywords:
- C4356
ms.assetid: 3af3defe-de33-43b6-bd6c-2c2e09e34f3f
ms.openlocfilehash: f110ee633fed1c3b43ecc06dadcc27fde4f14bde
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052023"
---
# <a name="compiler-warning-level-2-c4356"></a>Предупреждение компилятора (уровень 2) C4356

"член": статические данные не могут быть инициализированы через производный класс

Инициализация статических элементов данных была неправильно сформирована. Компилятор принял инициализацию. Чтобы избежать этого предупреждения, инициализируйте член с помощью базового класса.

Чтобы отключить это предупреждение, используйте директиву pragma [warning](../../preprocessor/warning.md) .

Следующий пример приводит к возникновению ошибки C4356:

```cpp
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