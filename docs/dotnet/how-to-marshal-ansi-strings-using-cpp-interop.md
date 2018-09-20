---
title: 'Практическое: маршалинг строк ANSI с использованием взаимодействия C++ | Документация Майкрософт'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], strings
- ANSI [C++], marshaling strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
ms.assetid: 5eda2eb6-5140-40f0-82cf-7ce171fffb45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d4a1a0cd8b9da5812e404f70dc999dfaf1606666
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383367"
---
# <a name="how-to-marshal-ansi-strings-using-c-interop"></a>Практическое руководство. Маршалирование строк ANSI с использованием взаимодействия C++

В этом разделе показано, как строки ANSI могут быть передан с помощью взаимодействия C++, но в .NET Framework <xref:System.String> представляет строки в формате Юникод, поэтому преобразование в ANSI это дополнительное действие. Для взаимодействия с другими типами строки, в следующих разделах:

- [Практическое руководство. Маршалинг строк Юникода с использованием взаимодействия C++](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Практическое руководство. Маршалинг строк COM с помощью взаимодействия C++](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

В следующем примере кода используются [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md) директивы #pragma управляемых и неуправляемых функций в одном файле, но эти функции взаимодействия таким же образом, если они определены в отдельных файлах. Так как файлы, содержащие только неуправляемые функции не обязательно должны быть скомпилированы с [/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md), они сохраняют свои характеристики производительности.

## <a name="example"></a>Пример

В примере демонстрируется передача строки ANSI из управляемого в неуправляемую функцию с помощью <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A>. Этот метод выделяет память в неуправляемой куче и возвращает адрес после выполнения преобразования. Это означает, что нет закрепления необходима (поскольку памяти в куче сборщика Мусора, не передается в неуправляемую функцию) и возврат IntPtr из <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> должны быть сняты явно или результаты к утечке памяти.

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

В следующем примере показано, маршалинг данных, необходимый для доступа к строки ANSI в управляемую функцию, которая вызывается коллекцией неуправляемой функции. Управляемая функция, получив исходной строки, можно использовать его напрямую или преобразовать его в строку, управляемых с помощью <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> метод, как показано.

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