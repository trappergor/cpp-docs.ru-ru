---
title: Ошибка компилятора C3006
ms.date: 11/04/2016
f1_keywords:
- C3006
helpviewer_keywords:
- C3006
ms.assetid: 449082ec-fd45-4c47-8ab3-ba6a719e4dc4
ms.openlocfilehash: a851c9b84a858cd4ac5cee11f0da90f99200c789
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301773"
---
# <a name="compiler-error-c3006"></a>Ошибка компилятора C3006

"предложение": в предложении директивы OpenMP "директива" отсутствует необходимый аргумент

В директиве OpenMP отсутствует ожидаемый аргумент.

Следующий пример приводит к возникновению ошибки C3006:

```c
// C3006.c
// compile with: /openmp
int main()
{
   #pragma omp parallel shared   // C3006
   // Try the following line instead:
   // #pragma omp parallel shared(x) {}

}
```
