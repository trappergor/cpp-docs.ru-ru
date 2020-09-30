---
title: Ошибка компилятора C3045
ms.date: 11/04/2016
f1_keywords:
- C3045
helpviewer_keywords:
- C3045
ms.assetid: 9351ba3e-3d3f-455f-ac90-a810fa9fd947
ms.openlocfilehash: fc5c2b526133ea0de70d11c3a01269436701de79
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506286"
---
# <a name="compiler-error-c3045"></a>Ошибка компилятора C3045

Ожидается составной оператор, следующий за директивой OpenMP "sections". Отсутствует "{"

Блок кода, ограниченный фигурными скобками, должен следовать за директивой [sections](../../parallel/openmp/reference/openmp-directives.md#sections-openmp) .

Следующий пример приводит к возникновению ошибки C3045:

```cpp
// C3045.cpp
// compile with: /openmp /c
#include "omp.h"

int main() {
   int n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
         ++n2;   // C3045

      #pragma omp sections   // OK
      {
         ++n3;
      }
   }
}
```
