---
title: Параметры компилятора
ms.date: 01/29/2018
helpviewer_keywords:
- cl.exe compiler
- x86 Visual C++ compiler
- ARM Visual C++ compiler
- compiler options, C++
- x64 Visual C++ compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
ms.openlocfilehash: 8b887b2b9da6f38cdc1cf7287a69bbad8e88b989
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50583889"
---
# <a name="compiler-options"></a>Параметры компилятора

CL.exe — это средство, которое управляет Microsoft Visual C++ (MSVC) C и C++ компиляторами и компоновщиком. CL.exe может выполняться только в операционных системах, поддерживающих Microsoft Visual Studio для Windows.

> [!NOTE]
> Это средство можно запустить только из командной строки разработчика Visual Studio. В системной командной строке или проводнике это невозможно. Дополнительные сведения см. в разделе [кода C/C++ на сборки в командной строке](../building-on-the-command-line.md).

Компиляторы создают общие объекта файла формат COFF объектных файлах (.obj). Компоновщик создает исполняемые файлы (.exe) или библиотеки динамической компоновки (DLL).

Обратите внимание на то, что все параметры компилятора чувствительны к регистру. Вы можете использовать косую черту (`/`) или тире (`-`) позволяет задать параметры компилятора.

Для компиляции без компоновки следует использовать [/c](../../build/reference/c-compile-without-linking.md) параметр.

## <a name="find-a-compiler-option"></a>Найти параметр компилятора

Чтобы найти конкретный параметр компилятора, см. в одном из следующих списков:

- [Параметры компилятора в алфавитном порядке](../../build/reference/compiler-options-listed-alphabetically.md)

- [Параметры компилятора, упорядоченные по категориям](../../build/reference/compiler-options-listed-by-category.md)

## <a name="specify-compiler-options"></a>Укажите параметры компилятора

В этой статье для каждого параметра компилятора рассматриваются, как его можно установить в среде разработки. Сведения о задании параметров за пределами среды разработки см. в разделе:

- [Синтаксис командной строки компилятора](../../build/reference/compiler-command-line-syntax.md)

- [Командные файлы компилятора CL](../../build/reference/cl-command-files.md)

- [Переменные среды CL](../../build/reference/cl-environment-variables.md)

## <a name="related-build-tools"></a>Связанные средства построения

[Параметры компоновщика](../../build/reference/linker-options.md) также влияют на построение программы.

## <a name="see-also"></a>См. также

[Справочные сведения о сборке C/C++](../../build/reference/c-cpp-building-reference.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[Быстрая компиляция](../../build/reference/fast-compilation.md)<br/>
[Вызов компоновщика компилятором CL](../../build/reference/cl-invokes-the-linker.md)
