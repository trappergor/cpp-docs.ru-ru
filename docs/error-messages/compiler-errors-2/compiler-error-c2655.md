---
title: Ошибка компилятора C2655
ms.date: 11/04/2016
f1_keywords:
- C2655
helpviewer_keywords:
- C2655
ms.assetid: beaefa6e-51b3-4df9-9150-960f3fbf40e0
ms.openlocfilehash: dbef9f00145c84a5c562915da966f2a49995c3ba
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756114"
---
# <a name="compiler-error-c2655"></a>Ошибка компилятора C2655

"идентификатор": определение или повторное объявление недопустимо в текущей области видимости

Идентификатор может быть повторно объявлен только в глобальной области видимости.

Следующий пример приводит к возникновению ошибки C2655:

```cpp
// C2655.cpp
class A {};
class B {
public:
   static int i;
};

int B::i;  // OK

int main() {
   A B::i;  // C2655
}
```
