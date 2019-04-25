---
title: Практическое руководство. Маршалинг массивов с помощью C++ Interop
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- arrays [C++], marshaling
- marshaling [C++], arrays
- interop [C++], arrays
- C++ Interop, arrays
- data marshaling [C++], arrays
ms.assetid: c2b37ab1-8acf-4855-ad3c-7d2864826b14
ms.openlocfilehash: 91fd86a547a0241f0cfcca7cfc36c204429d80ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324926"
---
# <a name="how-to-marshal-arrays-using-c-interop"></a>Практическое руководство. Маршалинг массивов с помощью C++ Interop

Эта статья описывает один аспект взаимодействия Visual C++. Дополнительные сведения см. в разделе [с помощью взаимодействия C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

В следующем примере кода используются [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md) директивы #pragma управляемых и неуправляемых функций в одном файле, но эти функции взаимодействия таким же образом, если они определены в отдельных файлах. Файлы, содержащие только неуправляемые функции не обязательно должны быть скомпилированы с [/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Пример

В следующем примере показан способ передачи управляемого массива в неуправляемую функцию. Управляемая функция использует [pin_ptr (C++выполняет)](../extensions/pin-ptr-cpp-cli.md) для подавления сборки мусора для массива до вызова неуправляемой функции. Предоставляя неуправляемая функция закрепляющий указатель в куче сборщика Мусора, можно избежать издержек на создания копии массива. Чтобы продемонстрировать, что неуправляемая функция получает доступ к куче сборщика Мусора, он изменяет содержимое массива, а изменения отражаются, когда управление возвращается управляемой функции.

```
// PassArray1.cpp
// compile with: /clr
#ifndef _CRT_RAND_S
#define _CRT_RAND_S
#endif

#include <iostream>
#include <stdlib.h>
using namespace std;

using namespace System;

#pragma unmanaged

void TakesAnArray(int* a, int c) {
   cout << "(unmanaged) array received:\n";
   for (int i=0; i<c; i++)
      cout << "a[" << i << "] = " << a[i] << "\n";

   unsigned int number;
   errno_t err;

   cout << "(unmanaged) modifying array contents...\n";
   for (int i=0; i<c; i++) {
      err = rand_s( &number );
      if ( err == 0 )
         a[i] = number % 100;
   }
}

#pragma managed

int main() {
   array<int>^ nums = gcnew array<int>(5);

   nums[0] = 0;
   nums[1] = 1;
   nums[2] = 2;
   nums[3] = 3;
   nums[4] = 4;

   Console::WriteLine("(managed) array created:");
   for (int i=0; i<5; i++)
      Console::WriteLine("a[{0}] = {1}", i, nums[i]);

   pin_ptr<int> pp = &nums[0];
   TakesAnArray(pp, 5);

   Console::WriteLine("(managed) contents:");
   for (int i=0; i<5; i++)
      Console::WriteLine("a[{0}] = {1}", i, nums[i]);
}
```

## <a name="example"></a>Пример

В следующем примере показано, передача неуправляемого массива для управляемой функции. Управляемая функция обращается к памяти массива напрямую (в отличие от создания управляемого массива и копировать содержимое массива), которое позволяет вносить изменения, сделанные управляемой функции отражаться в неуправляемую функцию, когда он восстанавливает элемент управления.

```
// PassArray2.cpp
// compile with: /clr
#include <iostream>
using namespace std;

using namespace System;

#pragma managed

void ManagedTakesAnArray(int* a, int c) {
   Console::WriteLine("(managed) array received:");
   for (int i=0; i<c; i++)
      Console::WriteLine("a[{0}] = {1}", i, a[i]);

   cout << "(managed) modifying array contents...\n";
   Random^ r = gcnew Random(DateTime::Now.Second);
   for (int i=0; i<c; i++)
      a[i] = r->Next(100);
}

#pragma unmanaged

void NativeFunc() {
   int nums[5] = { 0, 1, 2, 3, 4 };

   printf_s("(unmanaged) array created:\n");
   for (int i=0; i<5; i++)
      printf_s("a[%d] = %d\n", i, nums[i]);

   ManagedTakesAnArray(nums, 5);

   printf_s("(ummanaged) contents:\n");
   for (int i=0; i<5; i++)
      printf_s("a[%d] = %d\n", i, nums[i]);
}

#pragma managed

int main() {
   NativeFunc();
}
```

## <a name="see-also"></a>См. также

[Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
