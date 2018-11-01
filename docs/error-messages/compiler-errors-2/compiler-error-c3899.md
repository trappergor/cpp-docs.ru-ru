---
title: Ошибка компилятора C3899
ms.date: 11/04/2016
f1_keywords:
- C3899
helpviewer_keywords:
- C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
ms.openlocfilehash: 26860ba0e8fd92f491ee389147605ba82cecf25c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598397"
---
# <a name="compiler-error-c3899"></a>Ошибка компилятора C3899

«var»: l значения можно использовать данные-член initonly не допускается непосредственно внутри параллельной области в классе «класс»

[Initonly (C + +/ CLI)](../../dotnet/initonly-cpp-cli.md) не удается инициализировать член данных внутри той части параметра конструктор, который находится в [параллельных](../../parallel/openmp/reference/parallel.md) регион.  Это обусловлено тем, компилятор выполняет внутренний перемещение этого кода, таким образом, что это больше не является частью конструктора.

Чтобы устранить проблему, инициализируйте член данных initonly в конструкторе, но вне параллельной области.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3899.

```
// C3899.cpp
// compile with: /clr /openmp
#include <omp.h>

public ref struct R {
   initonly int x;
   R() {
      x = omp_get_thread_num() + 1000;   // OK
      #pragma omp parallel num_threads(5)
      {
         // cannot assign to 'x' here
         x = omp_get_thread_num() + 1000;   // C3899
         System::Console::WriteLine("thread {0}", omp_get_thread_num());
      }
      x = omp_get_thread_num() + 1000;   // OK
   }
};

int main() {
   R^ r = gcnew R;
   System::Console::WriteLine(r->x);
}
```