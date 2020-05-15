---
title: Экспорт из библиотеки DLL с использованием __declspec(dllexport)
ms.date: 05/06/2019
f1_keywords:
- dllexport
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- names [C++], DLL exports by
- export directives [C++]
- exporting DLLs [C++], __declspec(dllexport) keyword
ms.assetid: a35e25e8-7263-4a04-bad4-00b284458679
ms.openlocfilehash: 075962758773660085ae0b98b668c264524cc6aa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328593"
---
# <a name="exporting-from-a-dll-using-__declspecdllexport"></a>Экспорт из библиотеки DLL с использованием __declspec(dllexport)

С помощью ключевого слова **__declspec(dllexport)** вы можете экспортировать данные, функции, классы или функции-члены класса из библиотеки DLL. При использовании ключевого слова **__declspec(dllexport)** в объектный файл добавляется директива экспорта, поэтому необходимости в DEF-файле нет.

Это особенно удобно при экспорте дополненных имен функций C++. Поскольку стандартные соглашения о дополнении имен отсутствуют, имена экспортированных функций могут различаться в разных версиях компилятора. Если вы используете **__declspec(dllexport)** , перекомпиляция библиотеки DLL и зависимых EXE-файлов требуется только для того, чтобы учесть изменения в соглашениях об именовании.

Многие директивы экспорта, в том числе на основе порядковых номеров, а также NONAME и PRIVATE, могут определяться только в DEF-файле. Способов определить эти атрибуты без DEF-файла не существует. Тем не менее, если использовать **__declspec(dllexport)** вместе с DEF-файлом, ошибки сборки возникать не будут.

Для экспорта функций ключевое слово **__declspec(dllexport)** должно использоваться слева от ключевого слова соглашения о вызовах, если оно задано. Пример:

```
__declspec(dllexport) void __cdecl Function1(void);
```

Чтобы экспортировать все открытые члены данных и функции-члены в классе, это ключевое слово должно использоваться слева от имени класса следующим образом:

```
class __declspec(dllexport) CExampleExport : public CObject
{ ... class definition ... };
```

> [!NOTE]
> `__declspec(dllexport)` нельзя применять к функции с соглашением о вызовах `__clrcall`.

При построении библиотеки DLL, как правило, создается файл заголовка, который содержит прототипы функций и (или) экспортируемые классы, а также добавляется ключевое слово **__declspec(dllexport)** в раздел объявлений файла заголовка. Чтобы сделать код более удобочитаемым, определите макрос для **__declspec(dllimport)** , а затем используйте этот макрос для каждого экспортируемого символа:

```
#define DllExport   __declspec( dllexport )
```

**__declspec(dllexport)** сохраняет имена функций в таблице экспорта библиотеки DLL. Сведения об оптимизации размера этой таблицы см. в разделе [Экспорт функций из библиотеки DLL по порядковому номеру, а не по имени](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Экспорт из библиотеки DLL с использованием DEF-файлов](exporting-from-a-dll-using-def-files.md)

- [Экспорт и импорт с использованием AFX_EXT_CLASS](exporting-and-importing-using-afx-ext-class.md)

- [Экспорт функций на языке C++ для использования в исполняемых модулях, исходный код которых написан на языке C](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Экспорт функций на языке C для использования в исполняемых файлах, исходный код которых написан на языке C или C++](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Определение подходящего способа экспорта](determining-which-exporting-method-to-use.md)

- [Импорт в приложение с помощью __declspec(dllimport)](importing-into-an-application-using-declspec-dllimport.md)

- [Инициализация библиотеки DLL](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Ключевое слово __declspec](../cpp/declspec.md)

- [Импорт и экспорт встраиваемых функций](importing-and-exporting-inline-functions.md)

- [Взаимный импорт](mutual-imports.md)

## <a name="see-also"></a>См. также

[Экспорт из библиотеки DLL](exporting-from-a-dll.md)
