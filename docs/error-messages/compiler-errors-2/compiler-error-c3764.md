---
title: Ошибка компилятора C3764
ms.date: 11/04/2016
f1_keywords:
- C3764
helpviewer_keywords:
- C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
ms.openlocfilehash: 498aefae4dfe8fd13184b9da1685494d533575dd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556433"
---
# <a name="compiler-error-c3764"></a>Ошибка компилятора C3764

«переопределяющая_функция»: невозможно переопределить метод базового класса «базового класса»

Компилятор обнаружил переопределение неправильный формат. Например, функция базового класса не `virtual`. Дополнительные сведения см. в разделе [переопределить](../../windows/override-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3764.

```
// C3764.cpp
// compile with: /clr /c
public ref struct A {
   void g(int);
   virtual void h(int);
};

public ref struct B : A {
   virtual void g(int) override {}   // C3764
   virtual void h(int) override {}   // OK
};
```

## <a name="example"></a>Пример

C3764 также может возникнуть, когда метод базового класса — это явно и с именем переопределении. Следующий пример приводит к возникновению ошибки C3764.

```
// C3764_b.cpp
// compile with: /clr /c
ref struct A {
   virtual void Test() {}
};

ref struct B : public A {
   virtual void Test() override {}
   virtual void Test2() = A::Test {}   // C3764
};
```