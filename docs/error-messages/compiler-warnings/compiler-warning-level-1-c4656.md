---
title: Предупреждение компилятора (уровень 1) C4656
ms.date: 11/04/2016
f1_keywords:
- C4656
helpviewer_keywords:
- C4656
ms.assetid: b5aaef74-2320-4345-a6ae-b813881a491c
ms.openlocfilehash: 4285ce20f6131c2503304ed1bdb1bde02b2efcec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665690"
---
# <a name="compiler-warning-level-1-c4656"></a>Предупреждение компилятора (уровень 1) C4656

«символ»: тип данных новых было изменено с момента последней сборки или имеются разные объявления

Вы добавили или изменили тип данных, сделав его новым для исходного кода с момента последней успешной сборки. Функция "Изменить и продолжить" не поддерживает изменения существующих типов данных.

За этим предупреждением всегда будет следовать [неустранимая ошибка C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Дополнительные сведения см. в разделе [Поддерживаемые изменения кода](/visualstudio/debugger/supported-code-changes-cpp).

### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>Удаление данного предупреждения без завершения текущего сеанса отладки

1. Верните тип данных в его состояние до ошибки.

1. В меню **Отладка** выберите команду **Применить изменения кода**.

### <a name="to-remove-this-error-without-changing-your-source-code"></a>Устранение этой ошибки без изменения исходного кода

1. В меню **Отладка** выберите **Остановить отладку**.

1. В меню **Сборка** выберите **Сборка**.