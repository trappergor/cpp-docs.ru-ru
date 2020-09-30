---
title: Ошибка компилятора C3899
ms.date: 11/04/2016
f1_keywords:
- C3899
helpviewer_keywords:
- C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
ms.openlocfilehash: f3650d994e3102f71ab1d3598a4d1482f50b3334
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91510032"
---
# <a name="compiler-error-c3899"></a>Ошибка компилятора C3899

"var": использование l-value элемента данных initonly не допускается непосредственно в параллельной области в классе "класс"

Элемент данных [initonly (C++/CLI)](../../dotnet/initonly-cpp-cli.md) не может быть инициализирован внутри этой части конструктора, находящегося в [параллельной](../../parallel/openmp/reference/openmp-directives.md#parallel) области.  Это обусловлено тем, что компилятор выполняет внутреннее перемещение кода таким образом, что он фактически больше не является частью конструктора.

Чтобы устранить эту проблему, инициализируйте элемент данных initonly в конструкторе, но за пределами параллельной области.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3899.

```cpp
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
