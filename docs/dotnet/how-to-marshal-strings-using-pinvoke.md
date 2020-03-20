---
title: Практическое руководство. Маршалирование строк с помощью PInvoke
ms.custom: get-started-article
ms.date: 09/09/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- data marshaling [C++], strings
- platform invoke [C++], strings
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
ms.openlocfilehash: e89177261aa32d34ea392030078d4088ea61e2a5
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545225"
---
# <a name="how-to-marshal-strings-using-pinvoke"></a>Практическое руководство. Маршалирование строк с помощью PInvoke

В этом разделе объясняется, как можно вызывать собственные функции, которые принимают строки в стиле C, используя строковый тип CLR System:: String, используя .NET Framework поддержку вызова неуправляемого кода. Визуальным C++ программистам рекомендуется использовать функции C++ взаимодействия (если это возможно), поскольку P/Invoke предоставляет небольшие отчеты об ошибках во время компиляции, не является типобезопасным и может быть утомительным для реализации. Если неуправляемый API упакован в виде библиотеки DLL и исходный код недоступен, то единственным вариантом является P/Invoke, но в противном случае см. [раздел C++ использование Interop (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

Управляемые и неуправляемые строки размещаются в памяти по-разному, поэтому при передаче строк из управляемого кода в неуправляемые функции требуется атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute>, чтобы компилятор вставил необходимые механизмы преобразования для корректной и безопасной упаковки строковых данных.

Как и для функций, использующих только встроенные типы данных, <xref:System.Runtime.InteropServices.DllImportAttribute> используется для объявления управляемых точек входа в собственные функции, но для передачи строк вместо того, чтобы определять эти точки входа как строки в стиле C, вместо этого можно использовать описатель для типа <xref:System.String>. В этом случае компилятор попросит вставить код, выполняющий требуемое преобразование. Для каждого аргумента функции в неуправляемой функции, которая принимает строку, следует использовать атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute>, чтобы указать, что строковый объект должен быть упакован в собственную функцию в виде строки в стиле C.

Упаковщик упаковывает вызов неуправляемой функции в скрытую программу-оболочку, которая закрепляет и копирует управляемую строку в локально выделенную строку в неуправляемом контексте, который затем передается в неуправляемую функцию. Когда неуправляемая функция возвращает значение, программа-оболочка либо удаляет ресурс, либо, если она находилась в стеке, она освобождается, когда оболочка выходит за пределы области. Неуправляемая функция не несет ответственности за эту память. Неуправляемый код создает и удаляет память в куче, настроенной собственной библиотекой CRT, поэтому при использовании другой версии CRT никогда не возникает проблем с упаковкой.

Если неуправляемая функция возвращает строку в виде возвращаемого значения или выходного параметра, то маршалером копирует его в новую управляемую строку, а затем освобождает память. Дополнительные сведения см. в разделе [поведение маршалинга по умолчанию](/dotnet/framework/interop/default-marshaling-behavior) и [маршалинг данных с помощью вызова неуправляемого](/dotnet/framework/interop/marshaling-data-with-platform-invoke)кода.

## <a name="example"></a>Пример

Следующий код состоит из неуправляемого и управляемого модуля. Неуправляемый модуль — это библиотека DLL, которая определяет функцию с именем Такесастринг, которая принимает строку ANSI в стиле C в форме char *. Управляемый модуль — это приложение командной строки, которое импортирует функцию Такесастринг, но определяет ее как управляемую System. String вместо Char\*. Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> используется для указания способа маршалирования управляемой строки при вызове Такесастринг.

```cpp
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

```cpp
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

Этот метод приводит к созданию копии строки в неуправляемой куче, поэтому изменения, внесенные в строку с помощью собственной функции, не будут отражены в управляемой копии строки.

Обратите внимание, что ни одна часть библиотеки DLL не предоставляется управляемому коду через традиционную директиву #include. На самом деле библиотека DLL доступна только во время выполнения, поэтому проблемы с функциями, импортированными с `DllImport`, не обнаруживаются во время компиляции.

## <a name="see-also"></a>См. также:

[Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
