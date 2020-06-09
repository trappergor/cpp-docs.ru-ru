---
title: Одноэтапное и двухэтапное сборка объектов
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
ms.openlocfilehash: 07e006d5b326486c54f23990c604a7d2ee0e4c83
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625290"
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>Одноэтапное и двухэтапное сборка объектов

Вы можете выбрать один из двух способов создания графических объектов, таких как перья и кисти:

- *Одноэтапная конструкция*: создание и инициализация объекта на одном этапе с помощью конструктора.

- *Конструкция с двумя этапами*: создание и инициализация объекта на двух отдельных этапах. Конструктор создает объект, и инициализирует его функцию инициализации.

2-этапное построение всегда является более безопасным. В одноэтапном построении конструктор может вызвать исключение, если вы предпредоставите неверные аргументы или не удастся выделить память. Эта проблема не устранена конструкцией с двумя этапами, хотя необходимо проверить наличие сбоев. В любом случае уничтожение объекта будет таким же процессом.

> [!NOTE]
> Эти методы применяются для создания любых объектов, а не только для графических объектов.

## <a name="example-of-both-construction-techniques"></a>Пример обоих методов создания

В следующем кратком примере показаны оба метода создания объекта Pen:

[!code-cpp[NVC_MFCDocViewSDI#6](codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]

### <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Графические объекты](graphic-objects.md)

- [Выбор графического объекта в контексте устройства](selecting-a-graphic-object-into-a-device-context.md)

- [Контексты устройств](device-contexts.md)

- [Рисование в представлении](drawing-in-a-view.md)

## <a name="see-also"></a>См. также раздел

[Графические объекты](graphic-objects.md)
