---
title: Ошибка компилятора C3007
ms.date: 11/04/2016
f1_keywords:
- C3007
helpviewer_keywords:
- C3007
ms.assetid: e415ef42-bdc9-4f32-8198-5e25b289a089
ms.openlocfilehash: 9b80cc556887bf04efa3d98a31ccfd7ed1a2e4d7
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302280"
---
# <a name="compiler-error-c3007"></a>Ошибка компилятора C3007

arg: предложение в директиве "директива" OpenMP не принимает аргумент

В директиве OpenMP присутствовал аргумент, однако эта директива не принимает аргумент.

В следующем примере возникает ошибка C3007:

```c
// C3007.c
// compile with: /openmp
int main()
{
   #pragma omp parallel for ordered(2)   // C3007
}
```
