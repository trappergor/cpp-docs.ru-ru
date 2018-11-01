---
title: Ошибка компилятора C3797
ms.date: 11/04/2016
f1_keywords:
- C3797
helpviewer_keywords:
- C3797
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
ms.openlocfilehash: 2c8570edf16b9c002f9506b1b179a2ab36f7f26e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557538"
---
# <a name="compiler-error-c3797"></a>Ошибка компилятора C3797

«override»: объявление события не может содержать спецификатор переопределения (должен быть размещен в методах добавления/remove/raise событий вместо)

Не может переопределить тривиальное событие (событие без явно определенной акцессорами) с другой тривиального события. Переопределения событий необходимо определить его поведение с помощью функций доступа.

Дополнительные сведения см. в разделе [событий](../../windows/event-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3797.

```
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