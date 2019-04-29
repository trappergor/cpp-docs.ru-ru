---
title: Использование явного вызова Pinvoke в C++ (атрибут DllImport)
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling [C++], platform invoke
- C++ Interop, platform invoke
- interop [C++], platform invoke
- platform invoke [C++], marshaling in C++
- data marshaling [C++], platform invoke
ms.assetid: 18e5218c-6916-48a1-a127-f66e22ef15fc
ms.openlocfilehash: ee9d77920f04f7eba5112c66a906b02b7fc4a658
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384430"
---
# <a name="using-explicit-pinvoke-in-c-dllimport-attribute"></a>Использование явного вызова Pinvoke в C++ (атрибут DllImport)

.NET Framework предоставляет функции вызова неуправляемого кода (или PInvoke) с `Dllimport` атрибутом, позволяющим управляемым приложениям вызывать неуправляемые функции, поставляемые в библиотеках DLL. Явного вызова PInvoke является обязательным для ситуации, когда неуправляемых API упаковываются в виде библиотеки DLL и исходный код недоступен. Например, вызов функций Win32 требует PInvoke. В противном случае используйте неявные P {Invoke; см. описание [с помощью взаимодействия C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md) Дополнительные сведения.

Вызов PInvoke выполняется с помощью <xref:System.Runtime.InteropServices.DllImportAttribute>. Этот атрибут, который принимает имя библиотеки DLL в качестве первого аргумента, помещается перед объявлением функции для каждой точки входа библиотеки DLL, которая будет использоваться. Сигнатура функции должна соответствовать имени функции, экспортируемой библиотекой DLL (но некоторые преобразования типа может выполняться неявно путем определения `DllImport` объявления с точки зрения управляемых типов.)

Результатом является управляемую точку входа для каждой собственной функции библиотеки DLL, которая содержит необходимый код перехода (или преобразователь) и простые преобразования данных. Затем можно вызвать управляемые функции в DLL через эти точки входа. Код, вставленный в модуль, в результате вызова PInvoke, является полностью управляемым.

## <a name="in-this-section"></a>В этом разделе

- [Вызов неуправляемых функций из управляемого кода](../dotnet/calling-native-functions-from-managed-code.md)

- [Практическое руководство. Вызов собственных библиотек DLL из управляемого кода с помощью PInvoke](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)

- [Практическое руководство. Маршалирование строк с помощью PInvoke](../dotnet/how-to-marshal-strings-using-pinvoke.md)

- [Практическое руководство. Маршалирование структур с помощью PInvoke](../dotnet/how-to-marshal-structures-using-pinvoke.md)

- [Практическое руководство. Маршалирование массивов с помощью PInvoke](../dotnet/how-to-marshal-arrays-using-pinvoke.md)

- [Практическое руководство. Маршалирование указателей функций с помощью PInvoke](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)

- [Практическое руководство. Маршалирование внедренных указателей с помощью PInvoke](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)

## <a name="see-also"></a>См. также

[Вызов неуправляемых функций из управляемого кода](../dotnet/calling-native-functions-from-managed-code.md)
