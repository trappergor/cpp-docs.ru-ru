---
title: Параметры /Q (низкоуровневые операции)
ms.date: 01/23/2018
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: 6348226aa38d1f2eefdf9e19e27c4c87bd2f0812
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927673"
---
# <a name="q-options-low-level-operations"></a>Параметры /Q (низкоуровневые операции)

Параметры компилятора **/q** можно использовать для выполнения следующих низкоуровневых операций компилятора:

- [/Qfast_transcendentals (принудительная Быстрая трансцендентные функции)](qfast-transcendentals-force-fast-transcendentals.md): Создает быстрые трансцендентные функции.

- [/QIfist (отключение _ftol)](qifist-suppress-ftol.md): Подавляет, `_ftol` если требуется преобразование из типа с плавающей запятой в целочисленный тип (только архитектура x86).

- [/Qimprecise_fwaits (удаление fwaits внутри блоков try)](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): Удаляет команды `fwait` внутри блоков `try` .

- [/Qpar (авто-параллелизатора)](qpar-auto-parallelizer.md): Включает автоматическую параллелизацию циклов, которые помечены с помощью директивы [#pragma loop()](../../preprocessor/loop.md) .

- [/Qpar-report (авто Параллелизатора Reporting Level)](qpar-report-auto-parallelizer-reporting-level.md): Включает уровни отчетов для автоматической параллелизации.

- [/Qsafe_fp_loads](qsafe-fp-loads.md): Подавляет оптимизацию для загрузок регистров с плавающей запятой и перемещения между регистрами памяти и MMX.

- [/Qspectre](qspectre.md): Создает инструкции по устранению определенных уязвимостей системы безопасности устранением рисков Spectre.

- [/Qvec-report (авто векторизатора Reporting Level)](qvec-report-auto-vectorizer-reporting-level.md): Включает уровни отчетов для автоматической векторизации.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
