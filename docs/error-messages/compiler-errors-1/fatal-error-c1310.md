---
title: Неустранимая ошибка C1310
ms.date: 11/04/2016
f1_keywords:
- C1310
helpviewer_keywords:
- C1310
ms.assetid: ac48aa51-8023-42fe-b844-3f8bf228fbef
ms.openlocfilehash: 1b0fca9a5e453fd354a4efc6960a54386795ccf6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559081"
---
# <a name="fatal-error-c1310"></a>Неустранимая ошибка C1310

оптимизация, управляемая профилями, недоступна в OpenMP

Вы не сможете связать с [LTCG:PGI](../../build/reference/ltcg-link-time-code-generation.md) любой модуль, скомпилированный с параметром [/GL](../../build/reference/gl-whole-program-optimization.md).

В следующем примере возникает ошибка C1310:

```
// C1310.cpp
// compile with: /openmp /GL /link /LTCG:PGI
// C1310 expected
int main()
{
   int i = 0, j = 10;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 0; i++)
         --j;
   }
}
```