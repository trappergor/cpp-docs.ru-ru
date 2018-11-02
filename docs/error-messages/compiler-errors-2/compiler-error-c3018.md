---
title: Ошибка компилятора C3018
ms.date: 11/04/2016
f1_keywords:
- C3018
helpviewer_keywords:
- C3018
ms.assetid: 685be45f-f116-43a8-a88d-05ab6616e2f1
ms.openlocfilehash: 7a16c81cf2b9c2a815d2e35d10ae82d5a75547b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586970"
---
# <a name="compiler-error-c3018"></a>Ошибка компилятора C3018

"переменная1": в проверке или в приращении в операторе For директивы OpenMP должна использоваться переменная индекса "переменная2"

Цикл `for` в операторе OpenMP должен использовать ту же переменную для проверки и увеличения, которую он использует для индекса.

При компиляции следующего примера возникнет ошибка C3018:

```
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