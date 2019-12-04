---
title: Ошибка компилятора C2594
ms.date: 11/04/2016
f1_keywords:
- C2594
helpviewer_keywords:
- C2594
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
ms.openlocfilehash: ade657f9ada2a2249d2f96b7caada7b9719195d1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759338"
---
# <a name="compiler-error-c2594"></a>Ошибка компилятора C2594

"оператор": неоднозначные преобразования из "тип1" в "тип2"

Преобразование из *Type1* в *тип2* не было более прямым, чем другое. Мы предлагаем два возможных решения для преобразования из *Type1* в *тип тип2*. Первый вариант — определить прямое преобразование из *Type1* в *тип2*, а второй параметр — указать последовательность преобразований из типа *Type1* в *тип тип2*.

Следующий пример приводит к возникновению ошибки C2594. Предлагаемое разрешение ошибки представляет собой последовательность преобразований.

```cpp
// C2594.cpp
// compile with: /c
struct A{};
struct I1 : A {};
struct I2 : A {};
struct D : I1, I2 {};

A *f (D *p) {
   return (A*) (p);    // C2594

// try the following line instead
// return static_cast<A *>(static_cast<I1 *>(p));
}
```
