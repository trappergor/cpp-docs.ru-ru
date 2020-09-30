---
title: Ошибка компилятора C3042
ms.date: 11/04/2016
f1_keywords:
- C3042
helpviewer_keywords:
- C3042
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
ms.openlocfilehash: 8cd27f492a72277c383afa5ca335a073b1a0519c
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506394"
---
# <a name="compiler-error-c3042"></a>Ошибка компилятора C3042

Предложения "copyprivate" и "nowait" не могут указываться вместе в директиве "директива" OpenMP

Предложения [copyprivate](../../parallel/openmp/reference/openmp-clauses.md#copyprivate) и [nowait](../../parallel/openmp/reference/openmp-clauses.md#nowait) являются взаимоисключающими для конкретной директивы. Чтобы устранить эту ошибку, удалите одно из предложений `copyprivate` и `nowait` или оба.

В следующем примере возникает ошибка C3042:

```cpp
// C3042.cpp
// compile with: /openmp /c
#include <stdio.h>
#include "omp.h"

double d;

int main() {
    #pragma omp parallel private(d)
   {
      #pragma omp single copyprivate(d) nowait   // C3042
      {
      }
   }
}
```
