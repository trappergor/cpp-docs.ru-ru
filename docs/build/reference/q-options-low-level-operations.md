---
title: Параметры -Q (низкоуровневые операции) | Документы Microsoft
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
ms.openlocfilehash: c8a18c5d790cf21e8eb130a2b2baa152e20d79a1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375039"
---
# <a name="q-options-low-level-operations"></a>Параметры /Q (низкоуровневые операции)

Можно использовать **/q** параметры компилятора для выполнения следующих операций компилятора низкого уровня:

- [/ Qfast_transcendentals (принудительное использование быстрых трансцендентных функций)](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md): создает быстрые трансцендентные функции.

- [/ QIfist (отключение _ftol)](../../build/reference/qifist-suppress-ftol.md): подавляет `_ftol` при необходимости преобразования из типа с плавающей запятой в целочисленный тип является обязательным (x86 только).

- [/ Qimprecise_fwaits (удалить ожидания в блоке Try)](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): Удаляет `fwait` команды внутрь `try` блоков.

- [/ Qpar (автоматический Параллелизатор)](../../build/reference/qpar-auto-parallelizer.md): включает автоматическую параллелизацию циклов, которые отмечены [#pragma loop()](../../preprocessor/loop.md) директивы.

- [/ Qpar-report (уровень отчетности автоматического Параллелизатора)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md): включает уровни отчетов для автоматической параллелизации.

- [/ Qsafe_fp_loads](../../build/reference/qsafe-fp-loads.md): подавляет оптимизацию для регистре с плавающей запятой, загружает и перемещение между памяти и MMX регистры.

- [/ Qspectre](../../build/reference/qspectre.md): создает инструкции для устранения определенных Spectre уязвимостей безопасности.

- [/ Qvec-report (уровень отчетности автоматического Векторизатора)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md): включает уровни отчетов для автоматической векторизации.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)  
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)  
