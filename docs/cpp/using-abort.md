---
title: Использование функции abort
ms.date: 11/04/2016
f1_keywords:
- Abort
helpviewer_keywords:
- abort function
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
ms.openlocfilehash: 0961f6f88f5de4d435fa65e50b9dbdbc478e7608
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591832"
---
# <a name="using-abort"></a>Использование функции abort

Вызов [прервать](../c-runtime-library/reference/abort.md) функции приводит к немедленному завершению. Выполняется обход нормального процесса удаления для инициализированных глобальных статических объектов. Также осуществляется обход всей специальной обработки, которая была задана с помощью функции `atexit`.

## <a name="see-also"></a>См. также

[Дополнительные сведения о завершении](../cpp/additional-termination-considerations.md)