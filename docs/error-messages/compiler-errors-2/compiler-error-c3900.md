---
title: Ошибка компилятора C3900
ms.date: 11/04/2016
f1_keywords:
- C3900
helpviewer_keywords:
- C3900
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
ms.openlocfilehash: d031b55407d108b4f8be362156911bfae688326a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512363"
---
# <a name="compiler-error-c3900"></a>Ошибка компилятора C3900

«член»: не допускается в текущей области

Свойство блоки могут содержать объявления функций и определения встроенных функций только. Нет членов, отличных от функций разрешены в блоках свойств. Нет определения типов, операторы или дружественные функции допускаются. Дополнительные сведения см. в разделе [property](../../windows/property-cpp-component-extensions.md).

Определения событий может содержать только функции и методы доступа.

Следующий пример приводит к возникновению ошибки C3900:

```
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

```
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