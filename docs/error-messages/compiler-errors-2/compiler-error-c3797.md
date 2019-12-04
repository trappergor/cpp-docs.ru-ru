---
title: Ошибка компилятора C3797
ms.date: 11/04/2016
f1_keywords:
- C3797
helpviewer_keywords:
- C3797
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
ms.openlocfilehash: 7236cb75aef4250440a1e992415df07fb5b7da3f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757180"
---
# <a name="compiler-error-c3797"></a>Ошибка компилятора C3797

"override": объявление события не может иметь спецификатор переопределения (следует размещать в методах Add/Remove/raise события)

Нельзя переопределить тривиальное событие (событие без явно определенных методов доступа) другим тривиальным событием. Переопределяющее событие должно определять его поведение с помощью функций доступа.

Дополнительные сведения см. в разделе [event](../../extensions/event-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3797.

```cpp
// C3797.cpp
// compile with: /clr /c
delegate void MyDel();

ref class Class1 {
public:
   virtual event MyDel ^ E;
};

ref class Class2 : public Class1 {
public:
   virtual event MyDel ^ E override;   // C3797
};

// OK
ref class Class3 : public Class1 {
public:
   virtual event MyDel ^ E {
      void add(MyDel ^ d) override {}
      void remove(MyDel ^ d) override {}
   }
};
```
