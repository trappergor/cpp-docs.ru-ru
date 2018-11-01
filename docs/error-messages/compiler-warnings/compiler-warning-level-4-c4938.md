---
title: Предупреждение компилятора (уровень 4) C4938
ms.date: 11/04/2016
f1_keywords:
- C4938
helpviewer_keywords:
- C4938
ms.assetid: 6acac81a-9d23-465e-b700-ed4b6e8edcd0
ms.openlocfilehash: da2725a398a99b5943e128038e75622115a9e34f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50524557"
---
# <a name="compiler-warning-level-4-c4938"></a>Предупреждение компилятора (уровень 4) C4938

"переменная": переменная сокращения формата с плавающей точкой может привести к несогласованным результатам при использовании /fp:strict или #pragma fenv_access

Не следует использовать [/fp: strict](../../build/reference/fp-specify-floating-point-behavior.md) или [fenv_access](../../preprocessor/fenv-access.md) с сокращениями чисел с плавающей запятой OpenMP, так как сумма вычисляется в другом порядке. Таким образом, результаты могут отличаться от результатов вычислений без использования параметра /openmp.

При компиляции следующего примера будет выдано предупреждение C4938:

```
// C4938.cpp
// compile with: /openmp /W4 /fp:strict /c
// #pragma fenv_access(on)
extern double *a;

double test(int first, int last) {
   double sum = 0.0;
   #pragma omp parallel for reduction(+: sum)   // C4938
   for (int i = first ; i <= last ; ++i)
      sum += a[i];
   return sum;
}
```

Без явной параллелизации сумма вычисляется следующим образом:

```
sum = a[first] + a[first + 1] + ... + a[last];
```

С явной параллелизацией (и двумя потоками) сумма вычисляется следующим образом:

```
sum1 = a[first] + ... a[first + last / 2];
sum2 = a[(first + last / 2) + 1] + ... a[last];
sum = sum1 + sum2;
```