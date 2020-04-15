---
title: Общие сведения о маршалировании в C++
ms.date: 07/12/2019
ms.topic: reference
f1_keywords:
- marshaling
- marshalling
helpviewer_keywords:
- Visual C++, marshaling
- C++ Support Library, marshaling
- marshaling, about marshaling
ms.assetid: 997dd4bc-5f98-408f-b890-f35de9ce3bb8
ms.openlocfilehash: 0c7bf18fa823c6301a79c3f989efa73c9e8f628a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372011"
---
# <a name="overview-of-marshaling-in-ccli"></a>Обзор маршалинга в СЗ/КЛИ

В смешанном режиме иногда необходимо управлять данными между родными и управляемыми типами. *Библиотека маршалов* помогает вам переделать и преобразовать данные простым способом.  Библиотека маршалинга состоит из набора функций и `marshal_context` класса, выполняющего маршалинг для общих типов. Библиотека определяется в этих заголовках в каталоге **include/msclr** для вашего издания Visual Studio:

|Заголовок|Описание|
|---------------|-----------------|
|marshal.h|`marshal_context`функции маршалинга класса и контекста|
|marshal_atl.h| Функции для маршалинга типов ATL|
|marshal_cppstd.h|Функции для маршализации стандартных типов СЗ|
|marshal_windows.h|Функции для маршалинга типов Windows|

Путь по умолчанию для папки **msclr** является чем-то вроде этого в зависимости от того, какое издание у вас есть и номер сборки:

```cmd
C:\\Program Files (x86)\\Microsoft Visual Studio\\Preview\\Enterprise\\VC\\Tools\\MSVC\\14.15.26528\\include\\msclr
```

Вы можете использовать библиотеку маршалов с [классом marshal_context](../dotnet/marshal-context-class.md)или без нее. Некоторые преобразования требуют контекста. Другие преобразования могут быть реализованы с помощью [функции marshal_as.](../dotnet/marshal-as.md) В следующей таблице перечислены текущие поддерживаемые преобразования, требуется ли они контекста и какой файл маршала должен включать:

|От типа|Набрать|Метод маршала|Включить файл|
|---------------|-------------|--------------------|------------------|
|Система::Струна|const char \*|marshal_context|marshal.h|
|const char \*|Система::Струна|marshal_as|marshal.h|
|Char\*|Система::Струна|marshal_as|marshal.h|
|Система::Струна|Конст wchar_t\*|marshal_context|marshal.h|
|const wchar_t \*|Система::Струна|marshal_as|marshal.h|
|Wchar_t\*|Система::Струна|marshal_as|marshal.h|
|Система::IntPtr|HANDLE|marshal_as|marshal_windows.h|
|HANDLE|Система::IntPtr|marshal_as|marshal_windows.h|
|Система::Струна|BSTR|marshal_context|marshal_windows.h|
|BSTR|Система::Струна|marshal_as|marshal.h|
|Система::Струна|bstr_t|marshal_as|marshal_windows.h|
|bstr_t|Система::Струна|marshal_as|marshal_windows.h|
|Система::Струна|std::string|marshal_as|marshal_cppstd.h|
|std::string|Система::Струна|marshal_as|marshal_cppstd.h|
|Система::Струна|std::wstring|marshal_as|marshal_cppstd.h|
|std::wstring|Система::Струна|marshal_as|marshal_cppstd.h|
|Система::Струна|CStringT\<char>|marshal_as|marshal_atl.h|
|CStringT\<char>|Система::Струна|marshal_as|marshal_atl.h|
|Система::Струна|CStringT<wchar_t>|marshal_as|marshal_atl.h|
|CStringT<wchar_t>|Система::Струна|marshal_as|marshal_atl.h|
|Система::Струна|Ccombstr|marshal_as|marshal_atl.h|
|Ccombstr|Система::Струна|marshal_as|marshal_atl.h|

Маршалинг требует контекста только тогда, когда вы маршал от управляемых до родных типов данных и родной тип вы преобразуете в не имеет деструктатора для автоматической очистки. Контекст маршалинга уничтожает выделенный тип данных в своем деструктора. Таким образом, преобразования, требующие контекста, будут действительны только до тех пор, пока контекст не будет удален. Чтобы сохранить все маршированные значения, необходимо скопировать значения на собственные переменные.

> [!NOTE]
> Если у `NULL`вас есть встроенные s в строку, результат маршалинга строки не гарантируется. Встроенные `NULL`s могут привести к усечению строки или их сохранению.

В этом примере показано, как включить каталог msclr в объявление заголовка:

`#include "msclr\marshal_cppstd.h"`

Библиотека маршалов является расширительной, так что вы можете добавить свои собственные типы маршалов. Для получения дополнительной информации о расширении библиотеки маршалов [см.](../dotnet/how-to-extend-the-marshaling-library.md)

## <a name="see-also"></a>См. также раздел

[Библиотека поддержки СЗ](../dotnet/cpp-support-library.md)<br/>
[Практическое руководство. Расширение библиотеки маршалинга](../dotnet/how-to-extend-the-marshaling-library.md)
