---
title: Общие сведения о маршалинге в C++ | Документация Майкрософт
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- marshaling
- marshalling
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, marshaling
- C++ Support Library, marshaling
- marshaling, about marshaling
ms.assetid: 997dd4bc-5f98-408f-b890-f35de9ce3bb8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 60706a7922d9bea68e2ef4a27afa1401a1cd6920
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377452"
---
# <a name="overview-of-marshaling-in-c"></a>Общие сведения о маршалировании в C++

В смешанном режиме иногда необходимо выполнить маршалинг данных между неуправляемыми и управляемыми типами. Visual Studio 2008 появилась *библиотека маршалинга* для маршалинга и преобразования данных в простой способ.  Библиотека маршалинга состоит из набора функций и `marshal_context` класс, который выполняют маршалинг для типов. Библиотека определяется в эти заголовки в **включают msclr** каталог для других выпусков Visual Studio:

|Header|Описание|
|---------------|-----------------|
|Marshal.h|`marshal_context` класс и маршалинга функции, свободные контекста|
|marshal_atl.h| Функции для маршалинга типов ATL|
|marshal_cppstd.h|Функции для маршалинга стандартные типы C++|
|marshal_windows.h|Функции для маршалинга типов Windows|

Путь по умолчанию для **msclr** папка — нечто подобное в зависимости от того, какой выпуск имеется и номер сборки:

```cmd
C:\\Program Files (x86)\\Microsoft Visual Studio\\Preview\\Enterprise\\VC\\Tools\\MSVC\\14.15.26528\\include\\msclr
```

Библиотека маршалинга можно использовать с или без [класс marshal_context](../dotnet/marshal-context-class.md). Некоторые преобразования требуется контекст. Другие преобразования может быть реализован с помощью [marshal_as](../dotnet/marshal-as.md) функции. В следующей таблице перечислены текущего преобразования, поддерживаемые, требуется ли контекст и какой файл маршалинг необходимо включить:

|Из типа|Для ввода|Метод маршалинг|Включить файл|
|---------------|-------------|--------------------|------------------|
|System::String ^|const char \*|marshal_context|Marshal.h|
|const char \*|System::String ^|marshal_as|Marshal.h|
|Char \*|System::String ^|marshal_as|Marshal.h|
|System::String ^|const wchar_t\*|marshal_context|Marshal.h|
|const wchar_t \*|System::String ^|marshal_as|Marshal.h|
|wchar_t \*|System::String ^|marshal_as|Marshal.h|
|System::IntPtr|HANDLE|marshal_as|marshal_windows.h|
|HANDLE|System::IntPtr|marshal_as|marshal_windows.h|
|System::String ^|BSTR|marshal_context|marshal_windows.h|
|BSTR|System::String ^|marshal_as|Marshal.h|
|System::String ^|bstr_t|marshal_as|marshal_windows.h|
|bstr_t|System::String ^|marshal_as|marshal_windows.h|
|System::String ^|std::String|marshal_as|marshal_cppstd.h|
|std::String|System::String ^|marshal_as|marshal_cppstd.h|
|System::String ^|std::wstring|marshal_as|marshal_cppstd.h|
|std::wstring|System::String ^|marshal_as|marshal_cppstd.h|
|System::String ^|CStringT\<char >|marshal_as|marshal_atl.h|
|CStringT\<char >|System::String ^|marshal_as|marshal_atl.h|
|System::String ^|CStringT < wchar_t >|marshal_as|marshal_atl.h|
|CStringT < wchar_t >|System::String ^|marshal_as|marshal_atl.h|
|System::String ^|CComBSTR|marshal_as|marshal_atl.h|
|CComBSTR|System::String ^|marshal_as|marshal_atl.h|

Маршалинг требуется контекст, только в том случае, когда маршалинга из управляемого в машинный код данных типов и собственный тип, который необходимо преобразовать к имеет деструктор для автоматической очистки. Контекст маршалинга уничтожает выделенный собственного типа данных в деструкторе. Таким образом преобразований, которые требуется контекст будет действителен только в том случае, пока не будет удален в контексте. Чтобы сохранить все упакованные значения, необходимо скопировать значения собственные переменные.

> [!NOTE]
>  Если с внедренными `NULL`s в строке, маршалинг строки результат не гарантируется. Встроенный `NULL`s может привести к усечению строки, или они могут сохраняться.

В этом примере показано, как включить каталог msclr в объявлении заголовка include:

`#include "msclr\marshal_cppstd.h"`

Библиотека маршалинга является расширяемой, таким образом, можно добавить собственные маршалинга типов. Дополнительные сведения о расширении библиотеке маршалинга см. в разделе [как: расширение библиотеки маршалинга](../dotnet/how-to-extend-the-marshaling-library.md).

В более ранних версий, следует маршалировать данные с помощью [неуправляемого](/dotnet/framework/interop/consuming-unmanaged-dll-functions). Дополнительные сведения о `PInvoke`, см. в разделе [вызов собственных функций из управляемого кода](../dotnet/calling-native-functions-from-managed-code.md).

## <a name="see-also"></a>См. также

[Библиотека поддержки C++](../dotnet/cpp-support-library.md)<br/>
[Практическое руководство. Расширение библиотеки маршалинга](../dotnet/how-to-extend-the-marshaling-library.md)
