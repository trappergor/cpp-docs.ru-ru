---
title: Ошибка компилятора C3018
ms.date: 11/04/2016
f1_keywords:
- C3018
helpviewer_keywords:
- C3018
ms.assetid: 685be45f-f116-43a8-a88d-05ab6616e2f1
ms.openlocfilehash: 7d61bcb7364e90f5b5137f549989da769223a04f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742201"
---
# <a name="compiler-error-c3018"></a>Ошибка компилятора C3018

"переменная1": в проверке или в приращении в операторе For директивы OpenMP должна использоваться переменная индекса "переменная2"

Цикл `for` в операторе OpenMP должен использовать ту же переменную для проверки и увеличения, которую он использует для индекса.

При компиляции следующего примера возникнет ошибка C3018:

```cpp
// C3018.cpp
// compile with: /openmp
int main()
{
   int i = 0, j = 5;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; j < 10; ++i)   // C3018
      // try the following line instead
      // for (i = 0; i < 10; ++i)
         j *= 2;

      #pragma omp for
      for (i = 0; i < 10; j = j + i)   // C3018
      // try the following line instead
      // for (i = 0; i < 10; i = j + i)
         j *= 2;
   }
}
```
