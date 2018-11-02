---
title: Ошибка компилятора C3003
ms.date: 11/04/2016
f1_keywords:
- C3003
helpviewer_keywords:
- C3003
ms.assetid: 22e74f99-bb7f-4518-ab0d-934d5d49bcc7
ms.openlocfilehash: 6d15d8bde8855b8dcc4857492acdeb950731b503
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537557"
---
# <a name="compiler-error-c3003"></a>Ошибка компилятора C3003

"директива": имя директивы OpenMP не допускается после предложений директивы

Имя директивы OpenMP не может следовать после предложения директивы OpenMP.

Следующий пример приводит к возникновению ошибки C3003.

```
// C3003.c
// compile with: /openmp
int main()
{
   int x, y, z;
   #pragma omp parallel shared(x, y, z) for   // C3003
}
```