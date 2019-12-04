---
title: Ошибка компилятора C3203
ms.date: 11/04/2016
f1_keywords:
- C3203
helpviewer_keywords:
- C3203
ms.assetid: 6356770e-22c1-434c-91fe-f60b0aa23b91
ms.openlocfilehash: 1d0ed5ec717efecb9fbea4a9451836c0471522b6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738717"
---
# <a name="compiler-error-c3203"></a>Ошибка компилятора C3203

type: неспециализированный шаблон класса нельзя использовать в качестве аргумента шаблона или универсального аргумента для шаблонного или универсального параметра param, требуется действительный тип

Шаблонному или универсальному классу передан недопустимый аргумент. Шаблонный или универсальный класс ожидает тип в качестве параметра.

Эта ошибка может быть вызвана работой по согласованности компилятора, выполненной для Visual Studio 2005: неспециализированный шаблон класса нельзя использовать в качестве аргумента шаблона в списке базовых классов. Для устранения ошибки C3203 следует явным образом добавить параметры типов в имя класса шаблона при использовании его в качестве параметра шаблона в списке базовых классов.

```cpp
// C3203.cpp
template< typename T >
struct X {
   void f(X) {}
};

template< typename T >
struct Y : public X<Y> {   // C3203
// try the following line instead
// struct Y : public X<Y<T> > {
   void f(Y) {}
};

int main() {
   Y<int> y;
}
```

В следующем примере показано возникновение ошибки C3203 и приводятся сведения по ее устранению.

```cpp
// C3203_b.cpp
// compile with: /c
template <class T>
struct S1 {};

template <class T>
class C1 {};

typedef C1<S1> MyC1;   // C3203

// OK
template <template <class> class T>
class C2 {};

typedef C2<S1> MyC1;

template <class T>
class C3 {};

typedef C3<S1<int> > MyC12;
```

Ошибка C3203 также может возникнуть при использовании универсальных шаблонов.

```cpp
// C3203_c.cpp
// compile with: /clr /c
generic <class T>
value struct GS1 {};

generic <class T>
value struct GC1 {};

typedef GC1<GS1> MyGC1;   // C3203
typedef GC1<GS1<int> > MyGC2;   // OK
```
