---
title: Ошибка компилятора C3047
ms.date: 11/04/2016
f1_keywords:
- C3047
helpviewer_keywords:
- C3047
ms.assetid: 91c14566-5958-433d-8549-0e8bc3196f76
ms.openlocfilehash: c73cdce4520b139c872c29b7809a46f55c3bebd1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187635"
---
# <a name="compiler-error-c3047"></a>Ошибка компилятора C3047

Структурированному блоку в области OpenMP "sections" должна предшествовать директива "#pragma omp section"

Любой код в блоке кода, представленного директивой [sections](../../parallel/openmp/reference/sections-openmp.md) , должен быть в блоке кода, представленном директивой `section` .

Следующий пример приводит к возникновению ошибки C3047:

```
// C3047.cpp
// compile with: /openmp /c
#include "omp.h"

int main() {
   int n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
      {

         #pragma omp section
         {
            ++n3;
         }

         ++n2;   // C3047 not enclosed in #pragma omp section
      }
   }
}
```