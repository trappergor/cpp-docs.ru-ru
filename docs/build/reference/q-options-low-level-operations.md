---
title: Параметры /Q (низкоуровневые операции)
ms.date: 1/23/2018
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: a6dcbd256fa3510955884d3adba4855b23cdbfab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514261"
---
# <a name="q-options-low-level-operations"></a>Параметры /Q (низкоуровневые операции)

Можно использовать **/Q** параметры компилятора для выполнения следующих операций низкого уровня компилятора:

- [/ Qfast_transcendentals (принудительное использование быстрых трансцендентных функций)](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md): создает быстрые трансцендентные функции.

- [/ QIfist (Suppress _ftol)](../../build/reference/qifist-suppress-ftol.md): подавляет `_ftol` при преобразования из типа с плавающей запятой в целочисленный тип является обязательным (x86 только).

- [/ Qimprecise_fwaits (удалить ожидания в блоке Try)](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): Удаляет `fwait` команды внутри `try` блоков.

- [/ Qpar (автоматический Параллелизатор)](../../build/reference/qpar-auto-parallelizer.md): включает автоматическую параллелизацию циклов, которые помечены с [#pragma loop()](../../preprocessor/loop.md) директива.

- [/ Qpar-report (уровень отчетности автоматического Параллелизатора)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md): включает уровни отчетов для автоматической параллелизации.

- [/ Qsafe_fp_loads](../../build/reference/qsafe-fp-loads.md): замедляет процессы оптимизации регистре с плавающей запятой, загружает и переход между памятью и MMX регистрирует.

- [/ Qspectre](../../build/reference/qspectre.md): создает инструкции для устранения уязвимостей безопасности, определенных Spectre.

- [/ Qvec-report (уровень отчетности автоматического Векторизатора)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md): включает уровни отчетов для автоматической векторизации.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
