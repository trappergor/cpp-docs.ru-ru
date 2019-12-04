---
title: Ошибка компилятора C3900
ms.date: 11/04/2016
f1_keywords:
- C3900
helpviewer_keywords:
- C3900
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
ms.openlocfilehash: f1289fb9a4d60f2c75b54fd573c83064f1517282
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749104"
---
# <a name="compiler-error-c3900"></a>Ошибка компилятора C3900

"член": не допускается в текущей области

Блоки свойств могут содержать только объявления функций и встроенные определения функций. В блоках свойств не допускаются никакие члены, кроме функций. Не допускаются определения типов, операторы и дружественные функции. Для получения дополнительной информации см. [property](../../extensions/property-cpp-component-extensions.md).

Определения событий могут содержать только методы доступа и функции.

Следующий пример приводит к возникновению ошибки C3900:

```cpp
// C3900.cpp
// compile with: /clr
ref class X {
   property int P {
      void set(int);   // OK
      int i;   // C3900 variable declaration
   };
};
```

Следующий пример приводит к возникновению ошибки C3900:

```cpp
// C3900b.cpp
// compile with: /clr
using namespace System;
delegate void H();
ref class X {
   event H^ E {
      int m;   // C3900

      // OK
      void Test() {}

      void add( H^ h ) {}
      void remove( H^ h ) {}
      void raise( ) {}
   }
};
```
