---
title: Ошибка компилятора C2910
ms.date: 11/04/2016
f1_keywords:
- C2910
helpviewer_keywords:
- C2910
ms.assetid: 09c50e6a-e099-42f6-8ed6-d80e292a7a36
ms.openlocfilehash: 0061a7171dd08440ec5d8c8b8cadb77303ff8f41
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761119"
---
# <a name="compiler-error-c2910"></a>Ошибка компилятора C2910

"функция": не может быть явно специализированной

Компилятор обнаружил попытку выполнить явную специализацию функции дважды.

Следующий пример приводит к возникновению ошибки C2910:

```cpp
// C2910.cpp
// compile with: /c
template <class T>
struct S;

template <> struct S<int> { void f() {} };
template <> void S<int>::f() {}   // C2910 delete this specialization
```

C2910 также можно создать, если вы попытаетесь явно настроить член, не являющийся шаблоном. То есть можно явно настроить только шаблон функции.

Следующий пример приводит к возникновению ошибки C2910:

```cpp
// C2910b.cpp
// compile with: /c
template <class T> struct A {
   A(T* p);
};

template <> struct A<void> {
   A(void* p);
};

template <class T>
inline A<T>::A(T* p) {}

template <> A<void>::A(void* p){}   // C2910
// try the following line instead
// A<void>::A(void* p){}
```

Эта ошибка также будет сформирована в результате действий по согласованности компилятора, выполненных в Visual Studio .NET 2003:.

Для кода будет допустимым в версиях Visual Studio .NET 2003 и Visual Studio .NET визуального элемента C++, удалите `template <>`.

Следующий пример приводит к возникновению ошибки C2910:

```cpp
// C2910c.cpp
// compile with: /c
template <class T> class A {
   void f();
};

template <> class A<int> {
   void f();
};

template <> void A<int>::f() {}   // C2910
// try the following line instead
// void A<int>::f(){}   // OK
```
