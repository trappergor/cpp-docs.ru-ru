---
title: "Как: маршалинг строк ANSI с помощью взаимодействия C++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- interop [C++], strings
- ANSI [C++], marshaling strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
ms.assetid: 5eda2eb6-5140-40f0-82cf-7ce171fffb45
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7e70d62fa7a94a7278080c31f6650b31b71ff35b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-marshal-ansi-strings-using-c-interop"></a>Практическое руководство. Маршалирование строк ANSI с использованием взаимодействия C++
В этом разделе показано, как строки ANSI могут быть передана с помощью взаимодействия C++, однако платформа .NET Framework <xref:System.String> представляет строки в формате Юникод, поэтому преобразование в ANSI это дополнительное действие. Дополнительные сведения о взаимодействии с другими типами строки в следующих разделах:  
  
-   [Практическое руководство. Маршалинг строк Юникода с использованием взаимодействия C++](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [Практическое руководство. Маршалинг строк COM с помощью взаимодействия C++](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
 В следующем примере кода используются [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md) директивы #pragma управляемых и неуправляемых функций в одном файле, но эти функции взаимодействия так же, если они определены в отдельных файлах. Так как файлы, содержащие только неуправляемые функции, не обязательно должны быть скомпилированы с [/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md), они сохраняют свои характеристики производительности.  
  
## <a name="example"></a>Пример  
 В примере демонстрируется передача строку ANSI из управляемой в неуправляемую функцию с помощью <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A>. Этот метод выделяет память в неуправляемой куче и возвращает адрес после выполнения преобразования. Это означает, что не закрепление не требуется (поскольку памяти в куче сборщика Мусора, не передаются в неуправляемую функцию) и что IntPtr возвращен из <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> должны быть сняты явно или результаты утечка памяти.  
  
```  
// MarshalANSI1.cpp  
// compile with: /clr  
#include <iostream>  
#include <stdio.h>  
  
using namespace std;  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
void NativeTakesAString(const char* p) {  
   printf_s("(native) received '%s'\n", p);  
}  
  
#pragma managed  
  
int main() {  
   String^ s = gcnew String("sample string");  
   IntPtr ip = Marshal::StringToHGlobalAnsi(s);  
   const char* str = static_cast<const char*>(ip.ToPointer());  
  
   Console::WriteLine("(managed) passing string...");  
   NativeTakesAString( str );  
  
   Marshal::FreeHGlobal( ip );  
}  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано маршалируемые данные, необходимые для доступа к строки ANSI в управляемой функции, которая вызывается неуправляемой функции. Управляемой функции, после получения исходной строки, можно использовать его напрямую или преобразовать его в строку, управляемых с помощью <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> метода, как показано.  
  
```  
// MarshalANSI2.cpp  
// compile with: /clr  
#include <iostream>  
#include <vcclr.h>  
  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
  
void ManagedStringFunc(char* s) {  
   String^ ms = Marshal::PtrToStringAnsi(static_cast<IntPtr>(s));  
   Console::WriteLine("(managed): received '{0}'", ms);  
}  
  
#pragma unmanaged  
  
void NativeProvidesAString() {  
   cout << "(native) calling managed func...\n";  
   ManagedStringFunc("test string");  
}  
  
#pragma managed  
  
int main() {  
   NativeProvidesAString();  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)