---
title: Ошибка компилятора C2748
ms.date: 11/04/2016
f1_keywords:
- C2748
helpviewer_keywords:
- C2748
ms.assetid: b63ac78b-a200-499c-afea-15af1a1e819e
ms.openlocfilehash: a85ee151d9a4d62cc4b95248d669ff924365a95a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655641"
---
# <a name="compiler-error-c2748"></a>Ошибка компилятора C2748

при создании управляемого массива или массива WinRT следует указать размер массива или инициализатор массива

Неправильный формат управляемого массива или массива WinRT. Дополнительные сведения см. в описании [array](../../windows/arrays-cpp-component-extensions.md).

В следующем примере показано возникновение ошибки C2748 и приводятся сведения по ее устранению.

```
// C2748.cpp
// compile with: /clr
int main() {
   array<int> ^p1 = new array<int>();   // C2748
   // try the following line instead
   array<int> ^p2 = new array<int>(2);
}
```