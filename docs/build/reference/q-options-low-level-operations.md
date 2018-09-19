---
title: Параметры -Q (низкоуровневые операции) | Документация Майкрософт
ms.custom: ''
ms.date: 1/23/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /q
dev_langs:
- C++
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 15854333a9f26f87d20f7819327e68050ab37bf6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717794"
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
