---
title: Одноэтапное и двухэтапное сборка объектов
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
ms.openlocfilehash: 8f221ac6b63a06c65f932a695dfbf7b93ae7ac96
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375971"
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>Одноэтапное и двухэтапное сборка объектов

У вас есть выбор между двумя методами создания графических объектов, таких как ручки и кисти:

- *Одноступенчатая конструкция*: Построить и инициализировать объект в один этап, все с конструктором.

- *Двухступенчатая конструкция*: Построить и инициализировать объект в два отдельных этапа. Конструктор создает объект, и функция инициализации инициализирует его.

Двухступенчатая конструкция всегда безопаснее. При одноступенчатой конструкции конструктор может выбросить исключение, если вы предоставите неправильные аргументы или не удастся выделить память. Эта проблема избегается двухступенчатой конструкции, хотя вы должны проверить на неисправность. В любом случае, уничтожение объекта является одним и тем же процессом.

> [!NOTE]
> Эти методы применяются к созданию любых объектов, а не только графических объектов.

## <a name="example-of-both-construction-techniques"></a>Пример обеих строительных технологий

Следующий краткий пример показывает оба метода построения объекта пера:

[!code-cpp[NVC_MFCDocViewSDI#6](../mfc/codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]

### <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать больше о

- [Графические объекты](../mfc/graphic-objects.md)

- [Выбор графического объекта в контекст устройства](../mfc/selecting-a-graphic-object-into-a-device-context.md)

- [Контексты устройств](../mfc/device-contexts.md)

- [Рисование в представлении](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>См. также раздел

[Графические объекты](../mfc/graphic-objects.md)
