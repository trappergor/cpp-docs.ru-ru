---
title: Предупреждение компилятора (уровень 1) C4657
ms.date: 11/04/2016
f1_keywords:
- C4657
helpviewer_keywords:
- C4657
ms.assetid: eb750050-cea6-4ead-b80c-d5dcd4971cfc
ms.openlocfilehash: 6cc049d99339a6f19ca86cd5c7a10f062a1451a9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199504"
---
# <a name="compiler-warning-level-1-c4657"></a>Предупреждение компилятора (уровень 1) C4657

выражение включает тип данных, который обновился с момента последней сборки

Вы добавили или изменили тип данных, сделав его новым для исходного кода с момента последней успешной сборки. Функция "Изменить и продолжить" не поддерживает изменения существующих типов данных.

За этим предупреждением всегда будет следовать [неустранимая ошибка C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Дополнительные сведения см. в разделе [Поддерживаемые изменения кода](/visualstudio/debugger/supported-code-changes-cpp).

### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>Удаление данного предупреждения без завершения текущего сеанса отладки

1. Верните тип данных в его состояние до ошибки.

1. В меню **Отладка** выберите команду **Применить изменения кода**.

### <a name="to-remove-this-error-without-changing-your-source-code"></a>Устранение этой ошибки без изменения исходного кода

1. В меню **Отладка** выберите **Остановить отладку**.

1. В меню **Сборка** выберите **Сборка**.
