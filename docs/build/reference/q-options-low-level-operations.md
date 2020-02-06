---
title: Параметры /Q (низкоуровневые операции)
ms.date: 01/08/2020
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: 722a63a43e5e08fe80b26f908c7ae92df2fdb29c
ms.sourcegitcommit: 0f4ee9056d65043fa5a715f0ad1031c0ed30e2b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2020
ms.locfileid: "77034523"
---
# <a name="q-options-low-level-operations"></a>Параметры /Q (низкоуровневые операции)

Параметры компилятора **/q** можно использовать для выполнения следующих низкоуровневых операций компилятора:

- [/Qfast_transcendentals (принудительная Быстрая трансцендентные функции)](qfast-transcendentals-force-fast-transcendentals.md): создает быстрое трансцендентные функции.

- [/QIfist (отключение _ftol)](qifist-suppress-ftol.md): подавляет `_ftol`, если требуется преобразование из типа с плавающей запятой в целочисленный тип (только архитектура x86).

- [/Qimprecise_fwaits (удаление fwaits внутри блоков try)](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): удаляет команды `fwait` внутри блоков `try`.

- [/Кинтел-ЖКК-ерратум](qintel-jcc-erratum.md). снижает влияние на производительность, вызванное обновлением микрокода в условном коде Intel (ЖКК).

- [/Qpar (Auto-параллелизатора)](qpar-auto-parallelizer.md): включает автоматическую параллелизации циклов, которые помечены директивой [цикла #pragma ()](../../preprocessor/loop.md) .

- [/Qpar-report (Auto-Параллелизатора Report Level)](qpar-report-auto-parallelizer-reporting-level.md): включает уровни отчетов для автоматической параллелизации.

- [/Qsafe_fp_loads](qsafe-fp-loads.md): подавляет оптимизацию для загрузок регистров с плавающей запятой и перемещения между регистрами памяти и MMX.

- [/Qspectre](qspectre.md): создает инструкции по устранению некоторых уязвимостей системы безопасности устранением рисков Spectre.

- [/Кспектре-лоад](qspectre-load.md): создает инструкции по устранению уязвимостей безопасности устранением рисков Spectre, основанных на нагрузках.

- [/Кспектре-лоад-КФ](qspectre-load-cf.md): создает инструкции по устранению уязвимостей безопасности устранением рисков Spectre на основе инструкций потока управления, которые загружаются.

- [/Qvec-report (Auto-векторизатора Report Level)](qvec-report-auto-vectorizer-reporting-level.md): включает уровни отчетов для автоматической обработки векторов.

## <a name="see-also"></a>См. также раздел

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
