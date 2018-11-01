---
title: Предупреждение компилятора C4484
ms.date: 11/04/2016
f1_keywords:
- C4484
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
ms.openlocfilehash: 71a3d903ba32fecac4b2d8bfc3e0a93f19d0f4ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473180"
---
# <a name="compiler-warning-c4484"></a>Предупреждение компилятора C4484

«переопределяющая_функция»: соответствует методу базового класса «базового класса», но не помечен как «virtual», «new» или «override»; предполагается «new» (и не «virtual»)

При компиляции с параметром **/CLR**, компилятор не переопределяет неявно функцию базового класса, это означает, что функция получит новый слот в таблице vtable. Чтобы устранить, явно укажите, является ли функция переопределения.

Дополнительные сведения:

- [/clr (компиляция среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md)

- [override](../../windows/override-cpp-component-extensions.md)

- [New (новый слот в vtable)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)

C4484 всегда выдается как ошибка. Используйте [предупреждение](../../preprocessor/warning.md) директиву pragma, чтобы отключить предупреждение C4484.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4484.

```
// C4484.cpp
// compile with: /clr
ref struct A {
   virtual void Test() {}
};

ref struct B : A {
   void Test() {}   // C4484
};

// OK
ref struct C {
   virtual void Test() {}
   virtual void Test2() {}
};

ref struct D : C {
   virtual void Test() new {}
   virtual void Test2() override {}
};
```