---
title: Практическое руководство. Указатели функций маршалирования, использующие PInvoke
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- interop [C++], callbacks and delegates
- platform invoke [C++], callbacks and delegates
- marshaling [C++], callbacks and delegates
ms.assetid: dcf396fd-a91d-49c0-ab0b-1ea160668a89
ms.openlocfilehash: 2f12c86b7e32955622a4a2c598d01057e303a329
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435611"
---
# <a name="how-to-marshal-function-pointers-using-pinvoke"></a>Практическое руководство. Указатели функций маршалирования, использующие PInvoke

В этом разделе объясняется, как управляемые делегаты можно использовать вместо указателей функций при взаимодействии с неуправляемыми функциями, с помощью функции .NET Framework P/Invoke. Тем не менее программистам Visual C++, рекомендуется использовать возможности взаимодействия C++ (если возможно), поскольку P/Invoke предоставляет мало времени компиляции сведений об ошибках, не является строго типизированным и может быть утомительным. Если неуправляемый интерфейс API входит в состав библиотеки DLL и исходный код недоступен, P/Invoke является единственным параметром. В противном случае см. в разделах:

- [Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

- [Практическое руководство. Маршалинг обратных вызовов и делегатов посредством взаимодействия C++](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)

Неуправляемые API, принимающие указатели функций, как аргументы, которые могут вызываться из управляемого кода с помощью управляемого делегата собственного указателя функции. Компилятор автоматически маршалирует делегат неуправляемые функции, как указатель функции и вставляет код необходимости перехода с управляемым и неуправляемым кодом.

## <a name="example"></a>Пример

Следующий код состоит из неуправляемый и управляемый модуль. Неуправляемый модуль представляет собой DLL, определяет функцию TakesCallback, который принимает указатель на функцию. Этот адрес используется для выполнения функции.

Управляемый модуль определяет делегат, который маршалируется в собственный код как указатель на функцию и использует <xref:System.Runtime.InteropServices.DllImportAttribute> атрибут для предоставления собственной функции TakesCallback управляемому коду. В основной функции создается и передается функции TakesCallback экземпляра делегата. Выходные данные программы показано, что эта функция выполняется по собственной функции TakesCallback.

Управляемая функция подавляет сбор мусора для управляемого делегата, чтобы запретить сбор мусора .NET Framework перемещению делегата во время выполнения собственные функции.

```cpp
// TraditionalDll5.cpp
// compile with: /LD /EHsc
#include <iostream>
#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   /* Declare an unmanaged function type that takes two int arguments
      Note the use of __stdcall for compatibility with managed code */
   typedef int (__stdcall *CALLBACK)(int);
   TRADITIONALDLL_API int TakesCallback(CALLBACK fp, int);
}

int TakesCallback(CALLBACK fp, int n) {
   printf_s("[unmanaged] got callback address, calling it...\n");
   return fp(n);
}
```

```cpp
// MarshalDelegate.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

public delegate int GetTheAnswerDelegate(int);
public value struct TraditionalDLL {
   [DllImport("TraditionalDLL5.dll")]
   static public int TakesCallback(GetTheAnswerDelegate^ pfn, int n);
};

int GetNumber(int n) {
   Console::WriteLine("[managed] callback!");
   static int x = 0;
   ++x;
   return x + n;
}

int main() {
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);
   pin_ptr<GetTheAnswerDelegate^> pp = &fp;
   Console::WriteLine("[managed] sending delegate as callback...");

   int answer = TraditionalDLL::TakesCallback(fp, 42);
}
```

Обратите внимание, что часть библиотеки DLL предоставляется управляемого кода, с помощью стандартной #include. На самом деле, библиотеки DLL осуществляется во время выполнения, поэтому проблемы с функциями импортированы с <xref:System.Runtime.InteropServices.DllImportAttribute> не обнаруживаются во время компиляции.

## <a name="see-also"></a>См. также

[Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)