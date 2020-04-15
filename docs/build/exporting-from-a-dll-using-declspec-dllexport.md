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
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328593"
---
# <a name="exporting-from-a-dll-using-__declspecdllexport"></a>Экспорт из библиотеки DLL с использованием __declspec(dllexport)

Вы можете экспортировать данные, функции, функции, классифицируются или функции члена класса из DLL, используя ключевое слово **__declspec (dllexport).** **__declspec(dllexport)** добавляет директиву об экспорте в файл объекта, так что вам не нужно использовать файл .def.

Это удобство наиболее очевидно при попытке экспортировать украшенные названия функций СЗ. Поскольку нет стандартной спецификации для украшения имен, название экспортируемой функции может меняться между версиями компилятора. Если вы используете **__declspec (dllexport),** то перекомпиляция dLL и зависимых файлов .exe необходима только для учета любых изменений в конвенции именования.

Многие экспортные директивы, такие как ordinals, NONAME и PRIVATE, могут быть сделаны только в файле .def, и нет никакого способа указать эти атрибуты без файла .def. Однако использование **__declspec (dllexport)** в дополнение к использованию файла .def не вызывает ошибок сборки.

Для экспорта функций ключевое слово **__declspec (dllexport)** должно отображаться слева от ключевого слова calling-convention, если указано ключевое слово. Пример:

```
__declspec(dllexport) void __cdecl Function1(void);
```

Для экспорта всех открытых данных и функций членов в классе ключевое слово должно отображаться слева от имени класса следующим образом:

```
class __declspec(dllexport) CExampleExport : public CObject
{ ... class definition ... };
```

> [!NOTE]
> `__declspec(dllexport)`не могут быть применены `__clrcall` к функции с конвенцией вызова.

При создании DLL обычно создается файл заголовка, содержащий прототипы функций и/или классы, которые вы экспортируете, и добавляете **__declspec (dllexport)** в декларации в файле заголовка. Чтобы сделать код более читаемым, определите макрос для **__declspec (dllexport)** и используйте макрос с каждым символом, который вы экспортируете:

```
#define DllExport   __declspec( dllexport )
```

**__declspec (dllexport)** магазины функционируют имена в таблице экспорта DLL. Если вы хотите оптимизировать размер таблицы, [см. Функции экспорта из DLL от Ordinal, а не по имени](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).

## <a name="what-do-you-want-to-do"></a>Выбор действия

- [Экспорт из DLL с использованием файлов .def](exporting-from-a-dll-using-def-files.md)

- [Экспорт и импорт с использованием AFX_EXT_CLASS](exporting-and-importing-using-afx-ext-class.md)

- [Экспортные функции СЗЗ для использования в исполнителях C-языка](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Функции экспорта C для использования в исполнителях C или C-языка](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Определение подходящего способа экспорта](determining-which-exporting-method-to-use.md)

- [Импорт в приложение с помощью __declspec(dllimport)](importing-into-an-application-using-declspec-dllimport.md)

- [Инициализация DLL](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Ключевое слово __declspec](../cpp/declspec.md)

- [Импорт и экспорт встраиваемых функций](importing-and-exporting-inline-functions.md)

- [Взаимный импорт](mutual-imports.md)

## <a name="see-also"></a>См. также раздел

[Экспорт из библиотеки DLL](exporting-from-a-dll.md)
