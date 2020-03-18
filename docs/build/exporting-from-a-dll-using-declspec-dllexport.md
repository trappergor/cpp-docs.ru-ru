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
ms.openlocfilehash: c84a8eca25c90e0790ec8c4991d9d5a116afa59f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442527"
---
# <a name="exporting-from-a-dll-using-__declspecdllexport"></a>Экспорт из библиотеки DLL с использованием __declspec(dllexport)

Вы можете экспортировать данные, функции, классы или функции-члены класса из библиотеки DLL с помощью ключевого слова **__declspec (dllexport)** . **__declspec (dllexport)** добавляет директиву Export в объектный файл, чтобы не нужно было использовать DEF-файл.

Это удобство наиболее очевидно при попытке экспорта декорированных C++ имен функций. Поскольку для декорирования имен нет стандартной спецификации, имя экспортированной функции может измениться между версиями компилятора. При использовании **__declspec (dllexport)** перекомпиляция DLL и зависимых exe-файлов необходима только для того, чтобы учитывать любые изменения в соглашении об именовании.

Многие директивы экспорта, такие как Ordinal, NAME и PRIVATE, могут быть сделаны только в DEF-файле, и нет способа указать эти атрибуты без DEF-файла. Однако использование **__declspec (dllexport)** в дополнение к использованию DEF-файла не приводит к ошибкам сборки.

Для экспорта функций ключевое слово **__declspec (dllexport)** должно находиться слева от ключевого слова соглашения о вызовах, если указано ключевое слово. Пример:

```
__declspec(dllexport) void __cdecl Function1(void);
```

Чтобы экспортировать все открытые члены данных и функции-члены в классе, ключевое слово должно находиться слева от имени класса следующим образом:

```
class __declspec(dllexport) CExampleExport : public CObject
{ ... class definition ... };
```

> [!NOTE]
>  `__declspec(dllexport)` нельзя применить к функции с соглашением о вызовах `__clrcall`.

При создании библиотеки DLL обычно создается файл заголовка, содержащий прототипы функций и (или) экспортируемых классов, а также добавляется **__declspec (dllexport)** в объявления в файле заголовка. Чтобы сделать код более удобочитаемым, определите макрос для **__declspec (dllexport)** и используйте макрос с каждым экспортируемым символом:

```
#define DllExport   __declspec( dllexport )
```

**__declspec (dllexport)** хранит имена функций в таблице экспорта библиотеки DLL. Если требуется оптимизировать размер таблицы, см. раздел [Экспорт функций из библиотеки DLL по порядковому номеру, а не по имени](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).

## <a name="what-do-you-want-to-do"></a>Выбор действия

- [Экспорт из библиотеки DLL с помощью DEF-файлов](exporting-from-a-dll-using-def-files.md)

- [Экспорт и импорт с помощью AFX_EXT_CLASS](exporting-and-importing-using-afx-ext-class.md)

- [Экспорт C++ функций для использования в исполняемых файлах языка C](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Экспорт функций C для использования в исполняемых C++файлах c или языка](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Определение используемого метода экспорта](determining-which-exporting-method-to-use.md)

- [Импорт в приложение с помощью __declspec(dllimport)](importing-into-an-application-using-declspec-dllimport.md)

- [Инициализация библиотеки DLL](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Ключевое слово __declspec](../cpp/declspec.md)

- [Импорт и экспорт встраиваемых функций](importing-and-exporting-inline-functions.md)

- [Взаимный импорт](mutual-imports.md)

## <a name="see-also"></a>См. также раздел

[Экспорт из библиотеки DLL](exporting-from-a-dll.md)
