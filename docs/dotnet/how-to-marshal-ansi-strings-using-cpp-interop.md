---
title: Практическое руководство. Маршалирование строк ANSI с использованием взаимодействия C++
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- ANSI [C++], marshaling strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
ms.assetid: 5eda2eb6-5140-40f0-82cf-7ce171fffb45
ms.openlocfilehash: 3bdffa761bef74b9956842122b913e8213c736e9
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414572"
---
# <a name="how-to-marshal-ansi-strings-using-c-interop"></a>Практическое руководство. Маршалирование строк ANSI с использованием взаимодействия C++

В этом разделе показано, как можно передавать строки ANSI с помощью взаимодействия C++, но .NET Framework <xref:System.String> представляет строки в формате Юникода, поэтому преобразование в ANSI является дополнительным шагом. Сведения о взаимодействии с другими строковыми типами см. в следующих разделах:

- [Инструкции. маршалинг строк Юникода с помощью взаимодействия C++](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Инструкции. маршалинг строк COM с помощью взаимодействия C++](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

В следующих примерах кода используются [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md) директивы #pragma для реализации управляемых и неуправляемых функций в одном и том же файле, но эти функции взаимодействуют одинаково, если они определены в отдельных файлах. Поскольку файлы, содержащие только неуправляемые функции, не должны компилироваться с [параметром/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md), они могут хранить свои характеристики производительности.

## <a name="example-pass-ansi-string"></a>Пример. Передача строки ANSI

В примере демонстрируется передача строки ANSI из управляемой функции в неуправляемую с помощью <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> . Этот метод выделяет память в неуправляемой куче и возвращает адрес после выполнения преобразования. Это означает, что закрепление не требуется (так как память в куче сборщика мусора не передается в неуправляемую функцию) и что IntPtr, возвращенный из, <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> должен быть явно освобожден или приводит к утечке памяти.

```cpp
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

## <a name="example-data-marshaling-required-to-access-ansi-string"></a>Пример. для доступа к строке ANSI требуется маршалирование данных

В следующем примере показана упаковка данных, необходимая для доступа к строке ANSI в управляемой функции, которая вызывается неуправляемой функцией. Управляемая функция, при получении собственной строки, может либо использовать ее напрямую, либо преобразовать ее в управляемую строку с помощью <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> метода, как показано ниже.

```cpp
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

## <a name="see-also"></a>См. также раздел

[Использование взаимодействия C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
