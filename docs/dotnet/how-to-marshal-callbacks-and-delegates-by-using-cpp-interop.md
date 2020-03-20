---
title: Практическое руководство. Маршалинг обратных вызовов и делегатов посредством C++ Interop
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- C++ Interop, callbacks and delegates
- interop [C++], callbacks and delegates
- delegates [C++], marshaling
- marshaling [C++], callbacks and delegates
- callbacks [C++], marshaling
ms.assetid: 2313e9eb-5df9-4367-be0f-14b4712d8d2d
ms.openlocfilehash: 592eae0ff59baddb79b810d46669b78ecc801155
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "79544943"
---
# <a name="how-to-marshal-callbacks-and-delegates-by-using-c-interop"></a>Практическое руководство. Маршалинг обратных вызовов и делегатов посредством C++ Interop

В этом разделе демонстрируется маршалинг обратных вызовов и делегатов (управляемая версия обратного вызова) между управляемым и неуправляемым кодом с помощью C++Visual.

В следующих примерах кода используются [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md) директивы #pragma для реализации управляемых и неуправляемых функций в одном и том же файле, но функции также могут быть определены в отдельных файлах. Файлы, содержащие только неуправляемые функции, не должны компилироваться с параметром [/CLR (компиляция среды CLR)](../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Пример

В следующем примере показано, как настроить неуправляемый API для активации управляемого делегата. Создается управляемый делегат, а один из методов взаимодействия, <xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate%2A>, используется для получения базовой точки входа для делегата. Этот адрес затем передается в неуправляемую функцию, которая вызывает ее без знания того факта, что она реализована как управляемая функция.

Обратите внимание, что это возможно, но необязательно, чтобы закрепить делегат с помощью [pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md) , чтобы предотвратить его повторное размещение или удаление сборщиком мусора. Требуется защита от преждевременной сборки мусора, но закрепление обеспечивает более надежную защиту, чем требуется, так как это предотвращает сбор, но также предотвращает перемещение.

Если делегат перемещается с помощью сборки мусора, он не влияет на управляемый обратный вызов, поэтому <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> используется для добавления ссылки на делегат, позволяя переместить делегат, но не предотвращая реализацию. Использование GCHandle вместо pin_ptr сокращает потенциал фрагментации управляемой кучи.

```cpp
// MarshalDelegate1.cpp
// compile with: /clr
#include <iostream>

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

// Declare an unmanaged function type that takes two int arguments
// Note the use of __stdcall for compatibility with managed code
typedef int (__stdcall *ANSWERCB)(int, int);

int TakesCallback(ANSWERCB fp, int n, int m) {
   printf_s("[unmanaged] got callback address, calling it...\n");
   return fp(n, m);
}

#pragma managed

public delegate int GetTheAnswerDelegate(int, int);

int GetNumber(int n, int m) {
   Console::WriteLine("[managed] callback!");
   return n + m;
}

int main() {
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);
   GCHandle gch = GCHandle::Alloc(fp);
   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());
   Console::WriteLine("[managed] sending delegate as callback...");

// force garbage collection cycle to prove
// that the delegate doesn't get disposed
   GC::Collect();

   int answer = TakesCallback(cb, 243, 257);

// release reference to delegate
   gch.Free();
}
```

## <a name="example"></a>Пример

Следующий пример аналогичен предыдущему примеру, но в данном случае предоставленный указатель на функцию хранится неуправляемым API, поэтому его можно вызывать в любое время, что требует, чтобы сборка мусора была подавлена в произвольный промежуток времени. В результате в следующем примере используется глобальный экземпляр <xref:System.Runtime.InteropServices.GCHandle>, чтобы предотвратить переопределение делегата, независимо от области действия функции. Как обсуждалось в первом примере, использование pin_ptr не требуется для этих примеров, но в данном случае это не будет работать, так как область pin_ptr ограничена одной функцией.

```cpp
// MarshalDelegate2.cpp
// compile with: /clr
#include <iostream>

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

// Declare an unmanaged function type that takes two int arguments
// Note the use of __stdcall for compatibility with managed code
typedef int (__stdcall *ANSWERCB)(int, int);
static ANSWERCB cb;

int TakesCallback(ANSWERCB fp, int n, int m) {
   cb = fp;
   if (cb) {
      printf_s("[unmanaged] got callback address (%d), calling it...\n", cb);
      return cb(n, m);
   }
   printf_s("[unmanaged] unregistering callback");
   return 0;
}

#pragma managed

public delegate int GetTheAnswerDelegate(int, int);

int GetNumber(int n, int m) {
   Console::WriteLine("[managed] callback!");
   static int x = 0;
   ++x;

   return n + m + x;
}

static GCHandle gch;

int main() {
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);

   gch = GCHandle::Alloc(fp);

   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());
   Console::WriteLine("[managed] sending delegate as callback...");

   int answer = TakesCallback(cb, 243, 257);

   // possibly much later (in another function)...

   Console::WriteLine("[managed] releasing callback mechanisms...");
   TakesCallback(0, 243, 257);
   gch.Free();
}
```

## <a name="see-also"></a>См. также:

[Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
