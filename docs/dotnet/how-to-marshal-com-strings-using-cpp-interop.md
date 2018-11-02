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
ms.openlocfilehash: 664c9ed973e2dff4467d13742390da8a944eb87a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559124"
---
# <a name="how-to-marshal-com-strings-using-c-interop"></a>Практическое руководство. Маршалирование строк COM с помощью взаимодействия C++

В этом разделе показано, как BSTR (основной формат строк в программировании COM-) может быть передан из управляемого в неуправляемую функцию и наоборот. Взаимодействие с другими типами строк, см. в следующих разделах:

- [Практическое руководство. Маршалинг строк Юникода с использованием взаимодействия C++](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Практическое руководство. Маршалинг строк ANSI с использованием взаимодействия C++](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

В следующем примере кода используются [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md) директивы #pragma управляемых и неуправляемых функций в одном файле, но эти функции взаимодействия таким же образом, если они определены в отдельных файлах. Файлы, содержащие только неуправляемые функции не обязательно должны быть скомпилированы с [/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Пример

В следующем примере показано, как можно передать строку BSTR (формат строк в программировании COM) из управляемого в неуправляемую функцию. Вызов управляемой функции используется <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> получение адреса BSTR представления содержимого .NET System.String. Этот указатель закрепляется с помощью [pin_ptr (C + +/ CLI)](../windows/pin-ptr-cpp-cli.md) чтобы убедиться, что его физический адрес не меняется во время цикла сбора мусора во время выполнения неуправляемой функции. Сборщик мусора не освобождает перемещение памяти до [pin_ptr (C + +/ CLI)](../windows/pin-ptr-cpp-cli.md) выходит за пределы области.

```
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

В следующем примере показано, как можно передать строку BSTR из неуправляемой в неуправляемую функцию. Получение управляемой функции можно использовать строки в виде BSTR или <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> для преобразования его <xref:System.String> для использования в других управляемых функций. Поскольку память, представляющая строку BSTR, выделяется в неуправляемой куче, нет закрепления не требуется, так как отсутствует коллекция сборки мусора в неуправляемой куче.

```
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

## <a name="see-also"></a>См. также

[Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)