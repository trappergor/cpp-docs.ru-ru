---
title: Предупреждение компилятора C4484
ms.date: 11/04/2016
f1_keywords:
- C4484
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
ms.openlocfilehash: c168c91f8259b744ed10dd72701d34fd60b98681
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165162"
---
# <a name="compiler-warning-c4484"></a>Предупреждение компилятора C4484

"override_function": соответствует методу базового класса ссылки "base_class_function", но не помечен как "Virtual", "New" или "override"; предполагается "New" (а не "Virtual")

При компиляции с **параметром/CLR**компилятор не будет неявно переопределять функцию базового класса, что означает, что функция получит новый слот в таблице vtable. Чтобы устранить ошибку, явно укажите, является ли функция переопределением.

Дополнительные сведения см. в разделе:

- [/clr (компиляция среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md)

- [override](../../extensions/override-cpp-component-extensions.md)

- [new (новая ячейка в таблице vtable)](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md)

C4484 всегда выдается как ошибка. Чтобы отключить C4484, используйте директиву pragma [warning](../../preprocessor/warning.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4484.

```cpp
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
