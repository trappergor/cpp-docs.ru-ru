---
title: Ошибка компилятора C2594
ms.date: 11/04/2016
f1_keywords:
- C2594
helpviewer_keywords:
- C2594
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
ms.openlocfilehash: 75e3b438dd69f8879fdc2273a8f0357229941340
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386906"
---
# <a name="compiler-error-c2594"></a>Ошибка компилятора C2594

«operator»: неоднозначные преобразования из «типа1» в «тип2»

Нет преобразования *тип1* для *тип2* был более прямой, чем другие. Мы рекомендуем два возможных решения для преобразования из *тип1* для *тип2*. Первый способ — определить прямое преобразование из *тип1* для *тип2*, и второй вариант — указать последовательность преобразований из *тип1* для  *тип2*.

Следующий пример приводит к возникновению ошибки C2594. Предлагаемое разрешение для ошибки — это последовательность преобразований:

```
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