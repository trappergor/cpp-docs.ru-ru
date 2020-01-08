---
title: Ошибка компилятора C3010
ms.date: 11/04/2016
f1_keywords:
- C3010
helpviewer_keywords:
- C3010
ms.assetid: e959d038-bba6-432a-9c0a-0470474de7d9
ms.openlocfilehash: cbce65840280d3171ea84638b968686fa65633be
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302254"
---
# <a name="compiler-error-c3010"></a>Ошибка компилятора C3010

"метка": переход из структурированного блока OpenMP запрещен

Код не может переходить в блок OpenMP или из этого блока.

Следующий пример приводит к возникновению ошибки C3010.

```c
// C3010.c
// compile with: /openmp
int main() {
   #pragma omp parallel
   {
      #pragma omp parallel
      {
         goto lbl3;
      }
   }
   lbl3:;   // C3010
}
```
