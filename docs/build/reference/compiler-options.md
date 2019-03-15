---
title: Параметры компилятора MSVC
ms.date: 01/29/2018
helpviewer_keywords:
- cl.exe compiler
- x86 MSVC compiler
- ARM MSVC compiler
- compiler options, C++
- x64 MSVC compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
ms.openlocfilehash: 831aade72cd728ec42aee5ef1f320deb7bdf173d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816520"
---
# <a name="compiler-options"></a>Параметры компилятора

CL.exe — это средство, которое управляет Microsoft Visual C++ (MSVC) C и C++ компиляторами и компоновщиком. CL.exe может выполняться только в операционных системах, поддерживающих Microsoft Visual Studio для Windows.

> [!NOTE]
> Это средство можно запустить только из командной строки разработчика Visual Studio. В системной командной строке или проводнике это невозможно. Дополнительные сведения см. в разделе [использовать набор инструментов MSVC из командной строки](../building-on-the-command-line.md).

Компиляторы создают общие объекта файла формат COFF объектных файлах (.obj). Компоновщик создает исполняемые файлы (.exe) или библиотеки динамической компоновки (DLL).

Обратите внимание на то, что все параметры компилятора чувствительны к регистру. Вы можете использовать косую черту (`/`) или тире (`-`) позволяет задать параметры компилятора.

Для компиляции без компоновки следует использовать [/c](c-compile-without-linking.md) параметр.

## <a name="find-a-compiler-option"></a>Найти параметр компилятора

Чтобы найти конкретный параметр компилятора, см. в одном из следующих списков:

- [Параметры компилятора в алфавитном порядке](compiler-options-listed-alphabetically.md)

- [Параметры компилятора, упорядоченные по категориям](compiler-options-listed-by-category.md)

## <a name="specify-compiler-options"></a>Укажите параметры компилятора

В этой статье для каждого параметра компилятора рассматриваются, как его можно установить в среде разработки. Сведения о задании параметров за пределами среды разработки см. в разделе:

- [Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)

- [Командные файлы компилятора CL](cl-command-files.md)

- [Переменные среды CL](cl-environment-variables.md)

## <a name="related-build-tools"></a>Связанные средства построения

[Параметры компоновщика MSVC](linker-options.md) также влияют на построение программы.

## <a name="see-also"></a>См. также

[Справочные сведения о сборке C/C++](c-cpp-building-reference.md)<br/>
[Вызов компоновщика компилятором CL](cl-invokes-the-linker.md)
