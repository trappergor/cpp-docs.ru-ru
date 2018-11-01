---
title: Ошибка компилятора C3039
ms.date: 11/04/2016
f1_keywords:
- C3039
helpviewer_keywords:
- C3039
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
ms.openlocfilehash: 69be1b25254119108e517cee2f1e14368e0163f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511622"
---
# <a name="compiler-error-c3039"></a>Ошибка компилятора C3039

"переменная": переменная индекса в операторе for директивы OpenMP не может быть редукционной переменной

Переменная индекса является неявно частной, поэтому ее нельзя использовать в предложении [reduction](../../parallel/openmp/reference/reduction.md) в заключающей директиве [parallel](../../parallel/openmp/reference/parallel.md) .

## <a name="example"></a>Пример

При компиляции следующего примера возникнет ошибка C3039:

```
// C3039.cpp
// compile with: /openmp /c
int g_i;

int main() {
   int i;

   #pragma omp parallel reduction(+: i)
   {
      #pragma omp for
      for (i = 0; i < 10; ++i)   // C3039
         g_i += i;
   }
}
```