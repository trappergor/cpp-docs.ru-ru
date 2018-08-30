---
title: Предупреждение компилятора (уровень 1) C4655 | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4655
dev_langs:
- C++
helpviewer_keywords:
- C4655
ms.assetid: 540f2c7a-e4a1-49af-84b4-03eeea1bbf41
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9600c0fb9b4f03112ebd9cf430e3f833899c5f3c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209105"
---
# <a name="compiler-warning-level-1-c4655"></a>Предупреждение компилятора (уровень 1) C4655

> "*символ*": тип переменной с момента последней сборки или имеются разные объявления

## <a name="remarks"></a>Примечания

Вы изменили или добавили новый тип данных с момента последней успешной сборки. Функция "Изменить и продолжить" не поддерживает изменения существующих типов данных.

Это предупреждение сопровождается ошибкой [Неустранимая ошибка C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Дополнительные сведения см. в разделе [Поддерживаемые изменения кода](/visualstudio/debugger/supported-code-changes-cpp).

### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>Удаление данного предупреждения без завершения текущего сеанса отладки

1. Верните тип данных в его состояние до ошибки.

2. В меню **Отладка** выберите команду **Применить изменения кода**.

### <a name="to-remove-this-warning-without-changing-your-source-code"></a>Устранение данного предупреждения без изменения исходного кода

1. В меню **Отладка** выберите **Остановить отладку**.

2. В меню **Сборка** выберите **Сборка**.