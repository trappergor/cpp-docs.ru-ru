---
title: Ошибка компилятора C3225
ms.date: 11/04/2016
f1_keywords:
- C3225
helpviewer_keywords:
- C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
ms.openlocfilehash: 1caa1e7ce787ffc14e615c946b5d670c75e0332a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757622"
---
# <a name="compiler-error-c3225"></a>Ошибка компилятора C3225

аргумент универсального типа для "arg" не может быть "тип", он должен быть типом значения или типом обработчика

Аргумент универсального типа имеет неправильный тип.

Дополнительные сведения см. в статье [Универсальные шаблоны](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Пример

Нельзя создать экземпляр универсального типа с собственным типом. Следующий пример приводит к возникновению ошибки C3225.

```cpp
// C3225.cpp
// compile with: /clr
class A {};

ref class B {};

generic <class T>
ref class C {};

int main() {
   C<A>^ c = gcnew C<A>;   // C3225
   C<B^>^ c2 = gcnew C<B^>;   // OK
}
```

## <a name="example"></a>Пример

В следующем примере создается компонент с помощью C#. Обратите внимание, что ограничение указывает, что для универсального типа можно создать только тип значения.

```
// C3225_b.cs
// compile with: /target:library
// a C# program
public class MyList<T> where T: struct {}
```

## <a name="example"></a>Пример

Этот пример использует компонент, C#созданный с помощью, и нарушает ограничение, которое экземпляр милист может создавать только с типом значения, отличным от <xref:System.Nullable>. Следующий пример приводит к возникновению ошибки C3225.

```cpp
// C3225_c.cpp
// compile with: /clr
#using "C3225_b.dll"
ref class A {};
value class B {};
int main() {
   MyList<A> x;   // C3225
   MyList<B> y;   // OK
}
```
