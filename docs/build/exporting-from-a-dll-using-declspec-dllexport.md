---
title: Экспорт из библиотеки DLL с использованием __declspec(dllexport)
ms.date: 11/04/2016
f1_keywords:
- dllexport
- __declspec
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- names [C++], DLL exports by
- export directives [C++]
- exporting DLLs [C++], __declspec(dllexport) keyword
ms.assetid: a35e25e8-7263-4a04-bad4-00b284458679
ms.openlocfilehash: 48592fd6162ee354d82e73228e8b144ef0f354ed
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57420589"
---
# <a name="exporting-from-a-dll-using-declspecdllexport"></a>Экспорт из библиотеки DLL с использованием __declspec(dllexport)

Майкрософт ввел **__export** в версии 16-разрядный компилятор Visual C++, чтобы разрешить компилятору автоматически создавать экспортируемые имена и помещать их в LIB-файл. Затем этот LIB-файл можно использовать так же, как статический .lib для связывания с библиотекой DLL.

В новых версиях компилятора можно экспортировать данные, функции, классы и функции-члены класса из библиотеки DLL с помощью **__declspec(dllexport)** ключевое слово. **__declspec(dllexport)** добавляет директивы экспорта в объектный файл, поэтому необходимо создать DEF-файл.

Данное преимущество особенно заметно при экспорте декорированных имен функций C++. Так как нет стандартные спецификации по декорированию имен, имя экспортируемой функции может измениться между версиями компилятора. Если вы используете **__declspec(dllexport)**, перекомпиляция библиотеки DLL и .exe-файлов необходима только для учетной записи для изменений в соглашениях об именовании.

Большинство директив экспорта, такие как порядковые номера, NONAME и PRIVATE, можно указать только в DEF-файл, и нет способа указания данных атрибутов без DEF-файла. Тем не менее, с помощью **__declspec(dllexport)** наряду с DEF-файла не приводит к ошибкам построения.

Чтобы экспортировать функции, **__declspec(dllexport)** ключевое слово должно стоять слева от ключевого слова соглашения о вызовах, если оно задано. Пример:

```
__declspec(dllexport) void __cdecl Function1(void);
```

Чтобы экспортировать все открытые члены данных и функции-члены в класс, ключевое слово должно стоять слева от имени класса следующим образом:

```
class __declspec(dllexport) CExampleExport : public CObject
{ ... class definition ... };
```

> [!NOTE]
>  `__declspec(dllexport)` не может применяться к функции с помощью `__clrcall` соглашение о вызовах.

При построении библиотеки DLL, обычно создается файл заголовка, который содержит прототипы функций и классов при экспорте и добавьте **__declspec(dllexport)** объявления в файле заголовка. Чтобы сделать код более удобочитаемым, задайте макрос для **__declspec(dllexport)** и использовать его каждый символ, при экспорте:

```
#define DllExport   __declspec( dllexport )
```

**__declspec(dllexport)** сохраняет имена функций в таблице экспорта DLL. Если вы хотите оптимизировать размер таблицы, см. в разделе [Экспорт функций из библиотеки DLL по порядковому номеру, а не по имени](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).

> [!NOTE]
>  При переносе исходного кода библиотеки DLL с Win16 на Win32 необходимо заменить каждый экземпляр **__export** с **__declspec(dllexport)**.

Как ссылка поиск в файле заголовка Win32 Winbase.h. Он содержит примеры **__declspec(dllimport)** использования.

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Экспорт из DLL с использованием DEF-файлы](../build/exporting-from-a-dll-using-def-files.md)

- [Экспорт и импорт с использованием AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)

- [Экспорт функций C++ для использования в исполняемых файлах языка C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Экспорт функций на языке C для использования в исполняемых файлах C или C++-язык](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Определение подходящего метода экспорта для использования](../build/determining-which-exporting-method-to-use.md)

- [Импорт в приложение с помощью объявления __declspec(dllimport)](../build/importing-into-an-application-using-declspec-dllimport.md)

- [Инициализация библиотеки DLL](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [__Declspec-ключевое слово](../cpp/declspec.md)

- [Импорт и экспорт встраиваемых функций](../build/importing-and-exporting-inline-functions.md)

- [Взаимный импорт](../build/mutual-imports.md)

## <a name="see-also"></a>См. также

[Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)
