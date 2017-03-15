---
title: "Практическое руководство. Маршалинг обратных вызовов и делегатов посредством C++ Interop | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "взаимодействие C++, обратные вызовы и делегаты"
  - "обратные вызовы [C++], маршалинг"
  - "маршалинг данных [C++], обратные вызовы и делегаты"
  - "делегаты [C++], маршалинг"
  - "взаимодействие [C++], обратные вызовы и делегаты"
  - "маршалинг [C++], обратные вызовы и делегаты"
ms.assetid: 2313e9eb-5df9-4367-be0f-14b4712d8d2d
caps.latest.revision: 23
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Маршалинг обратных вызовов и делегатов посредством C++ Interop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе на примере Visual C\+\+ демонстрируется маршалинг обратных вызовов и делегатов \(обратных вызовов в управляемом коде\) между управляемым и неуправляемым кодом.  
  
 В приведенном ниже примере для реализации управляемых и неуправляемых функций в одном файле используются директивы \#pragma [managed, unmanaged](../preprocessor/managed-unmanaged.md). Тем не менее, эти функции можно определить и в раздельных файлах.  Файлы, содержащие только неуправляемые функции, не требуется компилировать с использованием параметра [\/clr \(компиляция CLR\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## Пример  
 В следующем примере показано, как настроить неуправляемый интерфейс API для вызова управляемого делегата.  Создается управляемый делегат, и один из методов взаимодействия, <xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate%2A>, используется для получения базовой точки входа делегата.  Затем этот адрес передается в неуправляемую функцию, которая использует его для вызова делегата, не зная, что эта функция реализована как управляемая.  
  
 Обратите внимание, что можно, хоть и не обязательно, использовать шаблон [pin\_ptr \(C\+\+\/CLI\)](../Topic/pin_ptr%20\(C++-CLI\).md) для закрепления делегата, чтобы не допустить его перемещение или удаление сборщиком мусора.  Защита от преждевременного удаления сборщиком мусора нужна, но закрепление обеспечивает большую степень защиты, чем это необходимо, так как предотвращает не только удаление, но и перемещение.  
  
 Если делегат перемещается сборщиком мусора, это не повлияет на него, поэтому для добавления ссылки на делегат используется метод <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> — это позволяет перемещать делегат, но предотвращает его удаление.  Использование GCHandle вместо pin\_ptr уменьшает потенциал фрагментации управляемой кучи.  
  
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
  
## Пример  
 Следующий пример похож на предыдущий, но в данном случае предоставляемый указатель на функцию сохраняется неуправляемым интерфейсом API, поэтому он может быть вызван в любое время, в связи с чем сборку мусора может потребоваться приостановить в произвольный момент времени.  Поэтому в примере используется глобальный экземпляр <xref:System.Runtime.InteropServices.GCHandle> для защиты от перемещения делегата, вне зависимости от его видимости в текущей функции.  Как пояснялось ранее, использование в этих примерах шаблона pin\_ptr является излишним, но в данном случае закрепляющий указатель все равно не будет работать, так как область видимости pin\_ptr ограничена одной функцией.  
  
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
  
## См. также  
 [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)