---
title: Ошибка компилятора C3003
ms.date: 11/04/2016
f1_keywords:
- C3003
helpviewer_keywords:
- C3003
ms.assetid: 22e74f99-bb7f-4518-ab0d-934d5d49bcc7
ms.openlocfilehash: 6d15d8bde8855b8dcc4857492acdeb950731b503
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152505"
---
# <a name="compiler-error-c3003"></a>Ошибка компилятора C3003

«директива»: Имя директивы OpenMP не допускается после предложений директивы

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