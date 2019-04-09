---
title: Ошибка компилятора C3900
ms.date: 11/04/2016
f1_keywords:
- C3900
helpviewer_keywords:
- C3900
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
ms.openlocfilehash: 35df94ccfcd7942f9057cb37ceee349c09b80607
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "58777419"
---
# <a name="compiler-error-c3900"></a>Ошибка компилятора C3900

«член»: не допускается в текущей области

Свойство блоки могут содержать объявления функций и определения встроенных функций только. Нет членов, отличных от функций разрешены в блоках свойств. Нет определения типов, операторы или дружественные функции допускаются. Дополнительные сведения см. в разделе [property](../../extensions/property-cpp-component-extensions.md).

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