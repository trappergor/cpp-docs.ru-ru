---
title: Ошибка компилятора C2425
ms.date: 11/04/2016
f1_keywords:
- C2425
helpviewer_keywords:
- C2425
ms.assetid: 0ce59404-9aff-4e01-aa8d-27d23e92eb30
ms.openlocfilehash: 3b723ecdc3544865aa4adb63c4fb21db62f4b726
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744658"
---
# <a name="compiler-error-c2425"></a>Ошибка компилятора C2425

'маркер' : неконстантное выражение в 'контексте'

Маркер образует часть выражения, не являющегося константой, в этом контексте.

Чтобы устранить эту проблему, замените маркер на константный литерал или на вычисление.

Следующий пример приводит к возникновению ошибки C2425:

```cpp
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
