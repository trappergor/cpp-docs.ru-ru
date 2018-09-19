---
title: Предупреждение компилятора (уровень 1) C4650 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4650
dev_langs:
- C++
helpviewer_keywords:
- C4650
ms.assetid: 3190b3e3-dcd6-4846-939b-f900ab652b2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d49b21452465f26d6e696f928c04c20dc0e33307
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052900"
---
# <a name="compiler-warning-level-1-c4650"></a>Предупреждение компилятора (уровень 1) C4650

Отладка не включена в предкомпилированный заголовок; будут доступны только глобальные символы из заголовка

Файл предкомпилированного заголовка не была скомпилирована с символьной отладочной информации Майкрософт.

При компоновке полученный исполняемый файл или динамически подключаемой библиотеки файл не будет содержать отладочную информацию для локальных символов, содержащихся в заголовке.

Это предупреждение можно избежать путем перекомпиляции предкомпилированного файла заголовка с [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) параметр командной строки.