---
title: Ошибка компилятора C3203
ms.date: 11/04/2016
f1_keywords:
- C3203
helpviewer_keywords:
- C3203
ms.assetid: 6356770e-22c1-434c-91fe-f60b0aa23b91
ms.openlocfilehash: 65b7e1d8f03b5e59bd21091531bc9d21472e4ae4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402740"
---
# <a name="compiler-error-c3203"></a>Ошибка компилятора C3203

type: неспециализированный шаблон класса нельзя использовать в качестве аргумента шаблона или универсального аргумента для шаблонного или универсального параметра param, требуется действительный тип

Шаблонному или универсальному классу передан недопустимый аргумент. Шаблонный или универсальный класс ожидает тип в качестве параметра.

Эта ошибка может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2005: шаблон неспециализированного класса нельзя использовать в качестве аргумента шаблона в списке базовых классов. Для устранения ошибки C3203 следует явным образом добавить параметры типов в имя класса шаблона при использовании его в качестве параметра шаблона в списке базовых классов.

```
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

```
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

```
// C3203_c.cpp
// compile with: /clr /c
generic <class T>
value struct GS1 {};

generic <class T>
value struct GC1 {};

typedef GC1<GS1> MyGC1;   // C3203
typedef GC1<GS1<int> > MyGC2;   // OK
```