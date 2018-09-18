---
title: Настройка обработки командной строки C | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- _spawn functions
- command line, processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line, processing arguments
- suppressing environment processing
- _exec function
ms.assetid: c20fa11d-b35b-4f3e-93b6-2cd5a1c3c993
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 541cfed194262aa5bff6810b19d5d2c89468ffa4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090819"
---
# <a name="customizing-c-command-line-processing"></a>Настройка обработки командной строки C

Если программа не принимает аргументы командной строки, можно сохранить небольшой объем пространства, подавив использование подпрограммы библиотеки, выполняющей обработку командной строки. Эта подпрограмма называется **_setargv** (или **_wsetargv** в окружении расширенных символов), как описано в статье [Wildcard Expansion](../c-language/expanding-wildcard-arguments.md) (Развертывание подстановочных знаков). Чтобы подавить ее использование, в файле, содержащем функцию **main**, определите подпрограмму с именем **_setargv** (или **_wsetargv** в окружении расширенных символов), которая не выполняет никаких действий. Тогда для вызовов **_setargv** и **_wsetargv** будет использоваться ваше определение **_setargv** или **_wsetargv**, а версия из библиотеки загружаться не будет.

Аналогичным образом, если вам не нужно обращаться к таблице окружения с помощью аргумента `envp`, вы можете предоставить собственную пустую подпрограмму вместо подпрограммы обработки окружения **_setenvp** (или **_wsetenvp**).

Если программа вызывает подпрограммы из семейства **_spawn** или **_exec**, определенные в библиотеке времени выполнения C, подпрограмму обработки окружения подавлять не следует, поскольку она используется для передачи окружения из вызывающего процесса в новый процесс.

## <a name="see-also"></a>См. также

[Функция main и выполнение программ](../c-language/main-function-and-program-execution.md)