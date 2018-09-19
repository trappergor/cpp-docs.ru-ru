---
title: Надежность | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.runtime
dev_langs:
- C++
helpviewer_keywords:
- robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a369698e0fcfc97b9713e0e1e5059115cce81dc7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104066"
---
# <a name="robustness"></a>Устойчивость

Используйте следующие функции библиотеки времени выполнения языка C, чтобы повысить надежность своей программы.

## <a name="run-time-robustness-functions"></a>Функции повышения надежности во время выполнения

|Функция|Использовать|
|--------------|---------|
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|Передает управление механизму обработки ошибок, если оператору **new** не удается выделить память.|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Обрабатывает исключения Win32 (структурированные исключения C) как типизированные исключения C++.|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Устанавливает собственную функцию завершения, которая будет вызываться [terminate](../c-runtime-library/reference/terminate-crt.md).|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Устанавливает собственную функцию завершения, которая будет вызываться [unexpected](../c-runtime-library/reference/unexpected-crt.md).|

## <a name="see-also"></a>См. также

[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>
[SetUnhandledExceptionFilter](https://msdn.microsoft.com/library/windows/desktop/ms680634.aspx)<br/>
