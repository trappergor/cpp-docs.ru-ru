---
title: Практическое руководство. Маршалирование строк COM с помощью взаимодействия C++
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- COM [C++], marshaling strings
ms.assetid: 06590759-bf99-4e34-a3a9-4527ea592cc2
ms.openlocfilehash: 8dfdad892261d5ae2d3494734458e1447f8ebd7c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545231"
---
# <a name="how-to-marshal-com-strings-using-c-interop"></a>Практическое руководство. Маршалирование строк COM с помощью взаимодействия C++

В этом разделе показано, как BSTR (базовый формат строки, предпочтительный в программировании COM) можно передать из управляемого в неуправляемую функцию и наоборот. Сведения о взаимодействии с другими типами строк см. в следующих разделах:

- [Практическое руководство. Маршалинг строк Юникода с использованием взаимодействия C++](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Практическое руководство. Маршалинг строк ANSI с использованием взаимодействия C++](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

В следующих примерах кода используются [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md) директивы #pragma для реализации управляемых и неуправляемых функций в одном и том же файле, но эти функции взаимодействуют одинаково, если они определены в отдельных файлах. Файлы, содержащие только неуправляемые функции, не должны компилироваться с [параметром/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Пример

В следующем примере показано, как BSTR (строковый формат, используемый в программировании COM) можно передать из управляемой функции в неуправляемую. Вызывающая управляемая функция использует <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> для получения адреса представления BSTR содержимого .NET System. String. Этот указатель закреплен с помощью [pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md) , чтобы гарантировать, что его физический адрес не изменяется во время цикла сборки мусора во время выполнения неуправляемой функции. Сборщику мусора запрещено перемещать память до тех пор, пока [pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md) не выйдет из области действия.

```cpp
// MarshalBSTR1.cpp
// compile with: /clr
#define WINVER 0x0502
#define _AFXDLL
#include <afxwin.h>

#include <iostream>
using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

void NativeTakesAString(BSTR bstr) {
   printf_s("%S", bstr);
}

#pragma managed

int main() {
   String^ s = "test string";

   IntPtr ip = Marshal::StringToBSTR(s);
   BSTR bs = static_cast<BSTR>(ip.ToPointer());
   pin_ptr<BSTR> b = &bs;

   NativeTakesAString( bs );
   Marshal::FreeBSTR(ip);
}
```

## <a name="example"></a>Пример

В следующем примере показано, как можно передать BSTR из неуправляемой функции в неуправляемую. Принимающая управляемая функция может либо использовать строку в качестве BSTR, либо использовать <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> для преобразования ее в <xref:System.String> для использования с другими управляемыми функциями. Поскольку память, представляющая BSTR, выделяется в неуправляемой куче, закрепление не требуется, так как в неуправляемой куче нет сборки мусора.

```cpp
// MarshalBSTR2.cpp
// compile with: /clr
#define WINVER 0x0502
#define _AFXDLL
#include <afxwin.h>

#include <iostream>
using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed

void ManagedTakesAString(BSTR bstr) {
   String^ s = Marshal::PtrToStringBSTR(static_cast<IntPtr>(bstr));
   Console::WriteLine("(managed) convered BSTR to String: '{0}'", s);
}

#pragma unmanaged

void UnManagedFunc() {
   BSTR bs = SysAllocString(L"test string");
   printf_s("(unmanaged) passing BSTR to managed func...\n");
   ManagedTakesAString(bs);
}

#pragma managed

int main() {
   UnManagedFunc();
}
```

## <a name="see-also"></a>См. также:

[Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
