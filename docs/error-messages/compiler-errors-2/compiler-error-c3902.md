---
title: Ошибка компилятора C3902
ms.date: 11/04/2016
f1_keywords:
- C3902
helpviewer_keywords:
- C3902
ms.assetid: feb3bb29-f836-4d77-ba71-3876f7f4f216
ms.openlocfilehash: 9dd98bc46e28fe54362de442a433736787cd0d07
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749065"
---
# <a name="compiler-error-c3902"></a>Ошибка компилятора C3902

"метод доступа": тип последнего параметра должен быть "тип"

Тип последнего параметра по крайней мере одного метода набора должен соответствовать типу свойства. Для получения дополнительной информации см. [property](../../extensions/property-cpp-component-extensions.md).

Следующий пример приводит к возникновению ошибки C3902:

```cpp
// C3902.cpp
// compile with: /clr /c
using namespace System;
ref class X {
   property String ^Name {
      void set(int);   // C3902
      // try the following line instead
      // void set(String^){}
   }

   property double values[int,int] {
      void set(int, int, float);   // C3902
      // try the following line instead
      // void set(int, int, double){}
   }
};
```
