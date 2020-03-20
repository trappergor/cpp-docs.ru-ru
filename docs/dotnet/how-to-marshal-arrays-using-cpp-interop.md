---
title: Практическое руководство. Упаковка и передача массивов с помощью взаимодействия C++
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- arrays [C++], marshaling
- marshaling [C++], arrays
- interop [C++], arrays
- C++ Interop, arrays
- data marshaling [C++], arrays
ms.assetid: c2b37ab1-8acf-4855-ad3c-7d2864826b14
ms.openlocfilehash: fddb8b4fa645d6fee3597d098fc67a3006603b9f
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "79544949"
---
# <a name="how-to-marshal-arrays-using-c-interop"></a>Практическое руководство. Упаковка и передача массивов с помощью взаимодействия C++

В этом разделе демонстрируется один аспект C++ визуальной совместимости. Дополнительные сведения см. [в разделе C++ использование взаимодействия (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

В следующих примерах кода используются [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md) директивы #pragma для реализации управляемых и неуправляемых функций в одном и том же файле, но эти функции взаимодействуют одинаково, если они определены в отдельных файлах. Файлы, содержащие только неуправляемые функции, не должны компилироваться с [параметром/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Пример

В следующем примере показано, как передать управляемый массив в неуправляемую функцию. Управляемая функция использует [pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md) , чтобы отключить сбор мусора для массива перед вызовом неуправляемой функции. Предоставляя неуправляемую функцию с закрепленным указателем в куче сборщика мусора, можно избежать издержек на создание копии массива. Чтобы продемонстрировать, что неуправляемая функция обращается к динамической памяти GC, она изменяет содержимое массива, и изменения отражаются, когда управляемая функция возобновляет управление.

```cpp
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

В следующем примере демонстрируется передача неуправляемого массива в управляемую функцию. Управляемая функция обращается к памяти массива напрямую (в отличие от создания управляемого массива и копирования содержимого массива), что позволяет отражать изменения, внесенные управляемой функцией, в неуправляемую функцию, когда она восстанавливает элемент управления.

```cpp
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

## <a name="see-also"></a>См. также:

[Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
