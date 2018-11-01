---
title: Одноэтапное и двухэтапное сборка объектов
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
ms.openlocfilehash: bdfb7879bc926435bdcd72d6776646c449ffef80
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623318"
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>Одноэтапное и двухэтапное сборка объектов

У вас есть выбор между двумя способами для создания графических объектов, таких как перья и кисти:

- *Одноэтапное конструкции*: конструкция и инициализацию объекта в один этап, все с конструктором.

- *Построение двухэтапное*: конструкция и инициализацию объекта в два отдельных этапа. Конструктор создает объект и функции инициализации инициализирует его.

Построение двухэтапное всегда является более безопасным. В конструкции одноэтапное конструктор может создания исключения, если предоставить неправильные аргументы или выделение памяти завершается сбоем. Эту проблему можно избежать с двухэтапной конструкции, несмотря на то, что у вас проверка неисправности. В любом случае уничтожения объекта имеет тот же процесс.

> [!NOTE]
>  Эти методы применяются при создании какие-либо объекты, не просто графические объекты.

## <a name="example-of-both-construction-techniques"></a>Пример того, обе методики построения

Краткий пример продемонстрированы оба способа создания объекта pen:

[!code-cpp[NVC_MFCDocViewSDI#6](../mfc/codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]

### <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Графические объекты](../mfc/graphic-objects.md)

- [Выбор графического объекта в контексте устройства](../mfc/selecting-a-graphic-object-into-a-device-context.md)

- [Контексты устройств](../mfc/device-contexts.md)

- [Рисование в представлении](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>См. также

[Графические объекты](../mfc/graphic-objects.md)

