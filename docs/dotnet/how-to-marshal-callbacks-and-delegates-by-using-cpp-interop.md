---
title: "Как: маршалинг обратных вызовов и делегатов посредством C++ Interop | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- C++ Interop, callbacks and delegates
- interop [C++], callbacks and delegates
- delegates [C++], marshaling
- marshaling [C++], callbacks and delegates
- callbacks [C++], marshaling
ms.assetid: 2313e9eb-5df9-4367-be0f-14b4712d8d2d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dbae96aeb7b11105a1a2aa30aa513c8d94011a91
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-marshal-callbacks-and-delegates-by-using-c-interop"></a>Практическое руководство. Маршалинг обратных вызовов и делегатов посредством C++ Interop
В этом разделе демонстрируется маршалинг обратных вызовов и делегатов (управляемую версию обратный вызов) между управляемым и неуправляемым кодом, с помощью Visual C++.  
  
 В следующем примере кода используются [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md) директивы #pragma управляемых и неуправляемых функций в одном файле, но также можно определить функции в отдельных файлах. Файлы, содержащие только неуправляемые функции, не обязательно должны быть скомпилированы с [/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как настроить неуправляемый интерфейс API для вызова управляемого делегата. Управляемый делегат и один из методов взаимодействия, <xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate%2A>, используется для получения базовой точки входа делегата. Затем этот адрес передается в неуправляемую функцию, которая вызывает его, не имея сведений о тот факт, что оно реализовано как управляемой функции.  
  
 Обратите внимание, что можно, но не требуется, чтобы закрепить делегата, с помощью [pin_ptr (C + +/ CLI)](../windows/pin-ptr-cpp-cli.md) чтобы не допустить его перемещение или удаление сборщиком мусора. Защита от преждевременное мусора требуется, но закрепление обеспечивает большую защиту, чем это необходимо, как он блокирует коллекции, но также предотвращает перемещение.  
  
 Если делегат перемещается сборщиком мусора, это не повлияет на него, поэтому <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> используется для добавления ссылки на этот делегат, позволяя перемещать делегат, но предотвращает его удаление. Использование GCHandle вместо pin_ptr уменьшает потенциал фрагментации управляемой кучи.  
  
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
 Следующий пример аналогичен предыдущему примеру, но в этом случае предоставляемый указатель на функцию сохраняется с неуправляемого интерфейса API, поэтому он может быть вызван в любое время, требование, что сборщик мусора может потребоваться приостановить произвольный момент времени. Поэтому в следующем примере используется глобальный экземпляр класса <xref:System.Runtime.InteropServices.GCHandle> чтобы предотвратить делегат перемещенный, независимо от области видимости функции. Как было описано в первом примере, с помощью pin_ptr нет необходимости в этих примерах, но в этом случае не будет работать в любом случае, как область видимости pin_ptr ограничена одной функции.  
  
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