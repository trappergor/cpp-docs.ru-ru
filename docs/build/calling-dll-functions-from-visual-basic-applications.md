---
title: Вызов функций библиотек DLL из приложений Visual Basic
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], calling DLL functions from Visual Basic
- DLL functions [C++]
- function calls [C++], DLL functions
- DLLs [C++], calling
- calling DLL functions from VB applications [C++]
- __stdcall keyword [C++]
- DLL functions [C++], calling
ms.assetid: 282f7fbf-a0f2-4b9f-b277-1982710be56c
ms.openlocfilehash: 8d792dac45d69a0857bda551d1f3c03fc3d03d1c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229887"
---
# <a name="calling-dll-functions-from-visual-basic-applications"></a>Вызов функций библиотек DLL из приложений Visual Basic

Для вызова функций на C или C++ из библиотеки DLL в приложениях на Visual Basic (или других языках, таких как Pascal или Fortran) эти функции необходимо экспортировать с использованием правильного соглашения о вызовах без какого-либо декорирования имен компилятором.

**`__stdcall`** создает правильное соглашение о вызове для функции (вызываемая функция очищает стек, а параметры передаются справа налево), но декорирует ее имя. Поэтому если для экспортированной функции в библиотеке DLL используется **`__declspec(dllexport)`** , экспортируется декорированное имя.

В декорированном имени **`__stdcall`** перед символьным именем добавляется символ подчеркивания ( **\_** ), а после символьного имени — символ **\@** , за которым следует число байтов в списке аргументов (необходимое пространство стека). В результате функция, объявленная как:

```C
int __stdcall func (int a, double b)
```

декорируется как `_func@12` в выходных данных.

Соглашение о вызовах C ( **`__cdecl`** ) декорирует имя как `_func`.

Чтобы получить декорированное имя, используйте [/MAP](reference/map-generate-mapfile.md). Использование **`__declspec(dllexport)`** приводит к следующим результатам:

- Если функция экспортируется с соглашением о вызовах C ( **`__cdecl`** ), из экспортируемого имени убирается начальный символ подчеркивания ( **\_** ).

- Если экспортируемая функция не использует соглашение о вызовах C (например, **`__stdcall`** ), экспортируется декорированное имя.

Так как переопределить место, где происходит очистка стека, невозможно, необходимо использовать **`__stdcall`** . Чтобы отменить декорирование имен при использовании **`__stdcall`** , необходимо указать их в виде псевдонимов в разделе EXPORTS файла DEF. Вот пример для следующего объявления функции:

```C
int  __stdcall MyFunc (int a, double b);
void __stdcall InitCode (void);
```

В файле DEF:

```
EXPORTS
   MYFUNC=_MyFunc@12
   INITCODE=_InitCode@0
```

Для вызова библиотек DLL программам, написанными на Visual Basic, необходимо использовать прием с файлом DEF, описанный в этой статье. Если псевдоним задается в программе Visual Basic, использовать псевдонимы в файле DEF необязательно. Это можно сделать в программе Visual Basic, добавив предложение alias в оператор [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement).

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Экспорт из библиотеки DLL](exporting-from-a-dll.md)

- [Экспорт из библиотеки DLL с использованием DEF-файлов](exporting-from-a-dll-using-def-files.md)

- [Экспорт из библиотеки DLL с использованием __declspec(dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

- [Экспорт функций на языке C++ для использования в исполняемых модулях, исходный код которых написан на языке C](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Определение подходящего способа экспорта](determining-which-exporting-method-to-use.md)

- [Внутренние имена](reference/decorated-names.md)

## <a name="see-also"></a>См. также

[Создание библиотек DLL C/C++ в Visual Studio](dlls-in-visual-cpp.md)
