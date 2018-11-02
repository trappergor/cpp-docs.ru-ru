---
title: Ошибка компилятора C3040
ms.date: 11/04/2016
f1_keywords:
- C3040
helpviewer_keywords:
- C3040
ms.assetid: 29e857ac-74f0-4ec6-becf-9026e38c160e
ms.openlocfilehash: b0bc4956cfc08ae50026827d78136a70b82d568e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474494"
---
# <a name="compiler-error-c3040"></a>Ошибка компилятора C3040

"var": тип переменной в предложении "reduction" не совместим с оператором редукции "оператор"

Переменную в предложении [reduction](../../parallel/openmp/reference/reduction.md) нельзя использовать с оператором редукции.

Следующий пример приводит к возникновению ошибки C3040:

```
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