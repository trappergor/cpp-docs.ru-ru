---
title: Ошибка компилятора C3020
ms.date: 11/04/2016
f1_keywords:
- C3020
helpviewer_keywords:
- C3020
ms.assetid: f625c7a3-afaa-4bd8-9c1b-51891b832f36
ms.openlocfilehash: cb32ceaf71d0a1c121b6e01e4b49f1db79a84d79
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506503"
---
# <a name="compiler-error-c3020"></a>Ошибка компилятора C3020

"var": переменная индекса цикла "for" OpenMP не может быть изменена в теле цикла

Цикл OpenMP **`for`** не может изменять индекс (счетчик цикла) в теле **`for`** цикла.

Следующий пример приводит к возникновению ошибки C3020:

```cpp
// C3020.cpp
// compile with: /openmp
int main() {
   int i = 0, n = 3;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 10; i += n)
         i *= 2;   // C3020
         // try the following line instead
         // n++;
   }
}
```

Переменная, объявленная с помощью [lastprivate](../../parallel/openmp/reference/openmp-clauses.md#lastprivate) , не может использоваться в качестве индекса внутри параллельного цикла.

Следующий пример предоставит C3020 для второго lastprivate, так как lastprivate запустит запись idx_a в самом внешнем цикле for. Первый lastprivate не выдает ошибку, поскольку lastprivate активирует запись в idx_a вне внешнего цикла for (технически, в самом конце последней итерации). Следующий пример приводит к возникновению ошибки C3020.

```cpp
// C3020b.cpp
// compile with: /openmp /c
float a[100][100];
int idx_a, idx_b;
void test(int first, int last)
{
   #pragma omp parallel for lastprivate(idx_a)
   for (idx_a = first; idx_a <= last; ++idx_a) {
      #pragma omp parallel for lastprivate(idx_a)   // C3020
      for (idx_b = first; idx_b <= last; ++idx_b) {
         a[idx_a][idx_b] += 1.0f;
      }
   }
}
```

В следующем примере показано возможное решение:

```cpp
// C3020c.cpp
// compile with: /openmp /c
float a[100][100];
int idx_a, idx_b;
void test(int first, int last)
{
   #pragma omp parallel for lastprivate(idx_a)
   for (idx_a = first; idx_a <= last; ++idx_a) {
      #pragma omp parallel for lastprivate(idx_b)
      for (idx_b = first; idx_b <= last; ++idx_b) {
         a[idx_a][idx_b] += 1.0f;
      }
   }
}
```
