---
title: Ошибка компилятора C2767
ms.date: 11/04/2016
f1_keywords:
- C2767
helpviewer_keywords:
- C2767
ms.assetid: e8f84178-a160-4d71-a236-07e4fcc11e96
ms.openlocfilehash: 6c13610b6fd7aae4b4232b836a0307867bd591d7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550154"
---
# <a name="compiler-error-c2767"></a>Ошибка компилятора C2767

управляемые или WinRTarray измерения несоответствие: требуется N аргументов, представлено M

Неправильный формат объявления управляемого массива или массива WinRT. Дополнительные сведения см. в описании [array](../../windows/arrays-cpp-component-extensions.md).

В следующем примере показано возникновение ошибки C2767 и приводятся сведения по ее устранению.

```
// C2767.cpp
// compile with: /clr
int main() {
   array<int> ^p1 = new array<int>(2,3); // C2767
   array<int> ^p2 = new array<int>(2);   // OK
}
```