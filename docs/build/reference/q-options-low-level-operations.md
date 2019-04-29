---
title: Параметры /Q (низкоуровневые операции)
ms.date: 1/23/2018
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: 5bbb63b4f437f8aefd5c84c1c1c4bd20bdb965cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319399"
---
# <a name="q-options-low-level-operations"></a>Параметры /Q (низкоуровневые операции)

Можно использовать **/Q** параметры компилятора для выполнения следующих операций низкого уровня компилятора:

- [/ Qfast_transcendentals (принудительное использование быстрых трансцендентных функций)](qfast-transcendentals-force-fast-transcendentals.md): Создает быстрые трансцендентные функции.

- [/ QIfist (подавление _ftol)](qifist-suppress-ftol.md): Подавляет `_ftol` при преобразования из типа с плавающей запятой в целочисленный тип является обязательным (x86 только).

- [/ Qimprecise_fwaits (удалить ожидания в блоке Try)](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): Удаляет команды `fwait` внутри блоков `try` .

- [/ Qpar (автоматический Параллелизатор)](qpar-auto-parallelizer.md): Включает автоматическую параллелизацию циклов, которые помечены с помощью директивы [#pragma loop()](../../preprocessor/loop.md) .

- [/ Qpar-report (уровень отчетности автоматического Параллелизатора)](qpar-report-auto-parallelizer-reporting-level.md): Включает уровни отчетов для автоматической параллелизации.

- [/ Qsafe_fp_loads](qsafe-fp-loads.md): Подавляет оптимизацию для загрузок регистре с плавающей запятой, а также для перемещения между памятью и регистры MMX.

- [/ Qspectre](qspectre.md): Создает инструкции для устранения уязвимостей безопасности, определенных Spectre.

- [/ Qvec-report (уровень отчетности автоматического Векторизатора)](qvec-report-auto-vectorizer-reporting-level.md): Включает уровни отчетов для автоматической векторизации.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
