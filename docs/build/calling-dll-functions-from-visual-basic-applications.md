---
title: Вызов функций библиотек DLL из приложений Visual Basic | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], calling DLL functions from Visual Basic
- DLL functions [C++]
- function calls [C++], DLL functions
- DLLs [C++], calling
- calling DLL functions from VB applications [C++]
- __stdcall keyword [C++]
- DLL functions [C++], calling
ms.assetid: 282f7fbf-a0f2-4b9f-b277-1982710be56c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b1cedafaea33ac642e3a5593468b996f2442bd50
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894568"
---
# <a name="calling-dll-functions-from-visual-basic-applications"></a>Вызов функций библиотек DLL из приложений Visual Basic

Для приложений Visual Basic (или приложения на других языках, например, Паскале или Фортране) и вызова функций из библиотеки DLL на C/C++ эти функции должны экспортироваться с использованием правильное соглашение о вызовах без декорирования имен компилятором

`__stdcall` Создает правильное соглашение о вызовах функции (вызываемая функция очищает стек и параметры передаются справа налево), но функция будут декорироваться. Поэтому, если **__declspec(dllexport)** используется для экспортируемой функции в библиотеке DLL, экспортируется декорированное имя.

`__stdcall` Декорирование имен, префиксы имени символа подчеркивания (_) и добавляет символ с символа (**\@**) за которым число байтов в списке аргументов (требуемый размер стека). В результате функция, объявленная как:

```C
int __stdcall func (int a, double b)
```

оформлен как `_func@12` в выходных данных.

Соглашение о вызовах C (`__cdecl`) экспортируемое имя как `_func`.

Чтобы получить декорированное имя, используйте [/MAP](../build/reference/map-generate-mapfile.md). Использование **__declspec(dllexport)** делает следующее:

- Если функция экспортируется с использованием соглашения о вызовах C (**_cdecl**), символа подчеркивания (_) удаляются при экспорте имя.

- Если экспортируемая функция не использует соглашение о вызовах C (например, `__stdcall`), экспортируется декорированное имя.

Поскольку нет способа переопределить порядок очистки стека, необходимо использовать `__stdcall`. Декорированное имена с `__stdcall`, необходимо указать их с помощью псевдонимов в разделе EXPORTS DEF-файла. Это показано ниже для в следующем объявлении функции:

```C
int  __stdcall MyFunc (int a, double b);
void __stdcall InitCode (void);
```

В. DEF-файл:

```
EXPORTS
   MYFUNC=_MyFunc@12
   INITCODE=_InitCode@0
```

Для библиотеки DLL, которая будет вызываться программ, написанных на Visual Basic технику псевдонимов, описанную в этом разделе требуется в DEF-файле. Если псевдоним создается в программе Visual Basic, создавать псевдоним в DEF-файл необязательно. Это можно сделать в программах на Visual Basic, добавив предложение псевдоним для [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement) инструкции.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)

- [Экспорт из библиотеки DLL с помощью. DEF-файлы](../build/exporting-from-a-dll-using-def-files.md)

- [Экспорт из DLL с использованием __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [Экспорт функций C++ для использования в исполняемых файлах языка C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Определение подходящего метода экспорта для использования](../build/determining-which-exporting-method-to-use.md)

- [Декорированные имена](../build/reference/decorated-names.md)

## <a name="see-also"></a>См. также

[DLL в Visual C++](../build/dlls-in-visual-cpp.md)
