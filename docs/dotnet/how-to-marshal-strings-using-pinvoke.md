---
title: 'Практическое: маршалинг строк с помощью PInvoke | Документация Майкрософт'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- data marshaling [C++], strings
- platform invoke [C++], strings
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d917228b1972715c291d84625cc684fc9de5b998
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396380"
---
# <a name="how-to-marshal-strings-using-pinvoke"></a>Практическое руководство. Маршалирование строк с помощью PInvoke

В этом разделе объясняется, как неуправляемый код функции, которые принимают строки в стиле C может вызываться с помощью строки CLR типа System::String, используя поддержку вызова платформы .NET Framework. Программистам Visual C++, рекомендуется использовать возможности взаимодействия C++ (если возможно), поскольку P/Invoke предоставляет мало времени компиляции сведений об ошибках, не является строго типизированным и может быть утомительным. Если неуправляемый интерфейс API входит в состав библиотеки DLL, а исходный код недоступен, P/Invoke является единственным параметром, но в противном случае см. в разделе [с помощью взаимодействия C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

Управляемые и неуправляемые строки располагаются по-разному в памяти, поэтому для передачи строк из управляемых функций в неуправляемые требуется <xref:System.Runtime.InteropServices.MarshalAsAttribute> атрибут, чтобы указать компилятору вставить необходимые механизмы преобразования для маршалинга строковых данных правильно и безопасно.

С помощью функций, использующих только встроенные типы данных, <xref:System.Runtime.InteropServices.DllImportAttribute> используется для объявления управляемых точек входа в неуправляемые функции, но для передачи строк вместо объявления этих точек входа, принимающие строки в стиле C, дескриптор <xref:System.String> типа можно использовать вместо этого. Вам предложат указать компилятору вставить код, который выполняет необходимые преобразования. Для каждого аргумента в неуправляемую функцию, которая принимает строку <xref:System.Runtime.InteropServices.MarshalAsAttribute> атрибут должен использоваться для указания, что строковый объект необходимо маршалировать в неуправляемую функцию строка C-стиля.

## <a name="example"></a>Пример

Следующий код состоит из неуправляемого и управляемого модуля. Неуправляемый модуль является библиотекой DLL, которая определяет функцию TakesAString, принимающая строку ANSI C-стиля в виде char *. Управляемый модуль является приложением командной строки, которое импортирует функцию TakesAString, но определена как принимающая управляемых System.String вместо char\*. <xref:System.Runtime.InteropServices.MarshalAsAttribute> Атрибут используется для указания того, как необходимо маршалировать управляемые строки при вызове TakesAString.

```
// TraditionalDll2.cpp
// compile with: /LD /EHsc
#include <windows.h>
#include <stdio.h>
#include <iostream>

using namespace std;

#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   TRADITIONALDLL_API void TakesAString(char*);
}

void TakesAString(char* p) {
   printf_s("[unmanaged] %s\n", p);
}
```

```
// MarshalString.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

value struct TraditionalDLL
{
   [DllImport("TraditionalDLL2.dll")]
      static public void
      TakesAString([MarshalAs(UnmanagedType::LPStr)]String^);
};

int main() {
   String^ s = gcnew String("sample string");
    Console::WriteLine("[managed] passing managed string to unmanaged function...");
   TraditionalDLL::TakesAString(s);
   Console::WriteLine("[managed] {0}", s);
}
```

Этот метод вызывает копию строки создаваться в неуправляемой куче, поэтому изменения, внесенные в строку функции в машинном коде не будут отражаться в управляемую копию строки.

Обратите внимание, что часть библиотеки DLL предоставляется управляемому коду через #include. На самом деле, библиотеки DLL осуществляется во время выполнения, поэтому проблемы с функциями импортированы с `DllImport` не обнаруживаются во время компиляции.

## <a name="see-also"></a>См. также

[Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)