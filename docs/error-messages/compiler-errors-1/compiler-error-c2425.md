---
title: Ошибка компилятора C2425
ms.date: 11/04/2016
f1_keywords:
- C2425
helpviewer_keywords:
- C2425
ms.assetid: 0ce59404-9aff-4e01-aa8d-27d23e92eb30
ms.openlocfilehash: fcbcf06df3330320bf014c132abc543e2e2e8087
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479029"
---
# <a name="compiler-error-c2425"></a>Ошибка компилятора C2425

'маркер' : неконстантное выражение в 'контексте'

Маркер образует часть выражения, не являющегося константой, в этом контексте.

Чтобы устранить эту проблему, замените маркер на константный литерал или на вычисление.

Следующий пример приводит к возникновению ошибки C2425:

```
// C2425.cpp
// processor: x86
int main() {
   int i = 3;
   __asm {
      mov eax, [ebp - i]   // C2425
      mov eax, [ebp - 3]   // OK
   }
}
```