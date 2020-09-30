---
title: Ошибка компилятора C3053
ms.date: 11/04/2016
f1_keywords:
- C3053
helpviewer_keywords:
- C3053
ms.assetid: ab9a25f3-e341-4f6e-8e69-069b4a963a64
ms.openlocfilehash: 8889388dc07f871bb60de44d317f9c8882795b03
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506188"
---
# <a name="compiler-error-c3053"></a>Ошибка компилятора C3053

"символ": "threadprivate" допускается только для глобальных или статических элементов данных

Символы, передаваемые в [threadprivate](../../parallel/openmp/reference/openmp-directives.md#threadprivate) , должны быть глобальными или статическими.

Следующий пример приводит к возникновению ошибки C3053.

```cpp
// C3053.cpp
// compile with: /openmp
void Test() {
   int x, y;
   #pragma omp threadprivate(x, y)   // C3053
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```

Возможное решение:

```cpp
// C3053b.cpp
// compile with: /openmp /LD
int x, y;
#pragma omp threadprivate(x, y)

void Test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```
