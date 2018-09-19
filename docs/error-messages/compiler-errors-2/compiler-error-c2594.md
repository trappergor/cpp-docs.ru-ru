---
title: Ошибка компилятора C2594 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2594
dev_langs:
- C++
helpviewer_keywords:
- C2594
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9be22544930bb94c36ec5906cbf60d5caac143fe
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058020"
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