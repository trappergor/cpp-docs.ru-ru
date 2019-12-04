---
title: Ошибка компилятора C2748
ms.date: 11/04/2016
f1_keywords:
- C2748
helpviewer_keywords:
- C2748
ms.assetid: b63ac78b-a200-499c-afea-15af1a1e819e
ms.openlocfilehash: e43defbf28c76dadcc7921ca76778413c41490a6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759637"
---
# <a name="compiler-error-c2748"></a>Ошибка компилятора C2748

при создании управляемого массива или массива WinRT следует указать размер массива или инициализатор массива

Неправильный формат управляемого массива или массива WinRT. Дополнительные сведения см. в описании [array](../../extensions/arrays-cpp-component-extensions.md).

В следующем примере показано возникновение ошибки C2748 и приводятся сведения по ее устранению.

```cpp
// C2748.cpp
// compile with: /clr
int main() {
   array<int> ^p1 = new array<int>();   // C2748
   // try the following line instead
   array<int> ^p2 = new array<int>(2);
}
```
