---
title: Устойчивость
ms.date: 11/04/2016
f1_keywords:
- c.runtime
helpviewer_keywords:
- robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
ms.openlocfilehash: 9244ba430efab01cd82b8ad773ad669470d67cff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454708"
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
