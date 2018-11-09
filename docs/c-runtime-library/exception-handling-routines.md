---
title: Процедуры обработки исключений
ms.date: 11/04/2016
f1_keywords:
- c.exceptions
helpviewer_keywords:
- exception handling, routines
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
ms.openlocfilehash: 09d58e49d3c9dc9b4b8ef40f725e927603e3e47c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507462"
---
# <a name="exception-handling-routines"></a>Процедуры обработки исключений

Использование функций обработки исключений C++ для восстановления после непредвиденных событий во время выполнения программы.

## <a name="exception-handling-functions"></a>Функции обработки исключений

|Функция|Использовать|
|--------------|---------|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Обрабатывает исключения Win32 (структурированные исключения C) как типизированные исключения C++|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Установите собственную подпрограмму завершения, чтобы ее можно было вызвать с помощью функции **terminate**|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Установите собственную функцию завершения, которая будет вызываться **unexpected**.|
|[terminate](../c-runtime-library/reference/terminate-crt.md)|Вызывается автоматически при определенных условиях после исключения. Функция **terminate** вызывает функцию **abort** или функцию, указанную с помощью **set_terminate**.|
|[unexpected](../c-runtime-library/reference/unexpected-crt.md)|Вызывает **terminate** или функцию, указанную с помощью **set_unexpected**. Функция **unexpected** не используется в текущей реализации обработчика исключений Microsoft C++.|

## <a name="see-also"></a>См. также

[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>
