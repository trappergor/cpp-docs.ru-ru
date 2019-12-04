---
title: Ошибка компилятора C3040
ms.date: 11/04/2016
f1_keywords:
- C3040
helpviewer_keywords:
- C3040
ms.assetid: 29e857ac-74f0-4ec6-becf-9026e38c160e
ms.openlocfilehash: 8a7ee7b814be1963e2d98b54e547cc5965eef9d3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754957"
---
# <a name="compiler-error-c3040"></a>Ошибка компилятора C3040

"var": тип переменной в предложении "reduction" не совместим с оператором редукции "оператор"

Переменную в предложении [reduction](../../parallel/openmp/reference/reduction.md) нельзя использовать с оператором редукции.

Следующий пример приводит к возникновению ошибки C3040:

```cpp
// C3040.cpp
// compile with: /openmp /c
#include "omp.h"
double d;

int main() {
   #pragma omp parallel reduction(&:d)   // C3040
      ;

   #pragma omp parallel reduction(-:d)  // OK
      ;
}
```
