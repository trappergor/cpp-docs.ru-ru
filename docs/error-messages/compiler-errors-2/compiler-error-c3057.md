---
title: Ошибка компилятора C3057 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3057
dev_langs:
- C++
helpviewer_keywords:
- C3057
ms.assetid: b0b2ba88-9c74-4bec-bf60-8fc72eade34c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b01c195ff05631f4bbf9d9d426f91dd94282d4bb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058824"
---
# <a name="compiler-error-c3057"></a>Ошибка компилятора C3057

"символ": динамическая инициализация символов threadprivate в настоящее время не поддерживается

Инициализированное значение символа, используемого в предложении [threadprivate](../../parallel/openmp/reference/threadprivate.md) , должно быть известно во время компиляции.

В следующем примере возникает ошибка C3057:

```
// C3057.cpp
// compile with: /openmp /c
extern int f();
int x, y = f();
int a, b;
#pragma omp threadprivate(x, y)   // C3057

#pragma omp threadprivate(a, b)

int main() {
   // Delete the following 4 lines to resolve.
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }

   #pragma omp parallel copyin(a, b)
   {
      a = b;
   }
}
```

В следующем примере возникает ошибка C3057:

```
// C3057b.cpp
// compile with: /openmp /c
extern int Initialize();
int main() {
   #pragma omp parallel
   {
      static int var = Initialize();
      #pragma omp threadprivate(var)   // C3057
   }

   // OK
   #pragma omp parallel
   {
      static int var2;
      static bool initialized2;
      #pragma omp threadprivate(var2, initialized2)
      if (!initialized2) {
         var2 = Initialize();
         initialized2 = true;
      }
   }
}
```