---
title: Практическое руководство. Маршалинг обратных вызовов и делегатов посредством взаимодействия C++
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
ms.openlocfilehash: f8088bf90162fd2177599c252b0eee6332d61289
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344954"
---
# <a name="how-to-marshal-callbacks-and-delegates-by-using-c-interop"></a>Практическое руководство. Маршалинг обратных вызовов и делегатов посредством взаимодействия C++

В этом разделе демонстрируется маршалинг обратных вызовов и делегатов (на управляемую версию обратный вызов) между управляемым и неуправляемым кодом, с помощью Visual C++.

В следующем примере кода используются [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md) директивы #pragma управляемых и неуправляемых функций в одном файле, но также можно определить функции в отдельных файлах. Файлы, содержащие только неуправляемые функции не обязательно должны быть скомпилированы с [/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Пример

Следующий пример демонстрирует настройку неуправляемый интерфейс API для вызова управляемого делегата. Создается управляемый делегат и один из методов взаимодействия, <xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate%2A>, используется для получения базовой точки входа для делегата. Затем этот адрес передается в неуправляемую функцию, которая вызывает его с помощью отсутствует информация о тот факт, что она реализуется как управляемой функции.

Обратите внимание, что возможно, но не обязательно, ПИН-код делегата, с помощью [pin_ptr (C++выполняет)](../extensions/pin-ptr-cpp-cli.md) чтобы не допустить его перемещение или удаление сборщиком мусора. Потребность в защите от преждевременное сборки мусора, но закрепление обеспечивает дополнительную защиту, чем это необходимо, так как он не позволяет коллекции, но также предотвращает перемещение.

Если делегат является сборщиком мусора, не влияет на него, поэтому <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> используется для добавления ссылки на делегат, позволяя перемещать делегат, но предотвращает его удаление. С помощью GCHandle вместо pin_ptr снижает потенциальный фрагментация управляемой кучи.

```
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

Следующий пример аналогичен предыдущему примеру, но в данном случае предоставляемый указатель на функцию хранит неуправляемый интерфейс API, поэтому его можно вызвать в любое время, требуя, что сборка мусора будет отключено для произвольный момент времени. Таким образом, в следующем примере используется глобальный экземпляр <xref:System.Runtime.InteropServices.GCHandle> чтобы предотвратить делегат перемещенный, независимо от области видимости функции. Как уже обсуждалось в первом примере, с помощью pin_ptr необязателен для этих примеров, но в этом случае не будут работать в любом случае, так как область видимости pin_ptr ограничена одной функции.

```
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

## <a name="see-also"></a>См. также

[Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
