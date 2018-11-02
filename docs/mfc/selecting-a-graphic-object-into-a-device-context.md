---
title: Выбор графического объекта в контексте устройства
ms.date: 11/04/2016
helpviewer_keywords:
- graphic objects [MFC], selecting into device context
- SelectObject method [MFC]
- GDI objects [MFC], device contexts
- lifetime, graphic objects [MFC]
- device contexts, selecting graphic objects into
- device contexts, graphic objects [MFC]
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
ms.openlocfilehash: c879369d445a9330139eff89be4ad8153252bfa1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438831"
---
# <a name="selecting-a-graphic-object-into-a-device-context"></a>Выбор графического объекта в контексте устройства

Этот раздел относится к с помощью графических объектов в контексте устройства окна. После того как вы [создайте графический объект](../mfc/one-stage-and-two-stage-construction-of-objects.md), необходимо выбрать его в контекст устройства вместо объект по умолчанию, хранящиеся в ней:

[!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/cpp/selecting-a-graphic-object-into-a-device-context_1.cpp)]

## <a name="lifetime-of-graphic-objects"></a>Время существования графических объектов

Графический объект, возвращенный [SelectObject](../mfc/reference/cdc-class.md#selectobject) «временный». То есть будет удалена при [OnIdle](../mfc/reference/cwinapp-class.md#onidle) функция-член класса `CWinApp` времени при очередном программа получает простоя. До тех пор, пока используется объект, возвращаемый `SelectObject` единственную функцию без возвращения управления основной цикл обработки сообщений, будет иметь никаких проблем.

### <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Графические объекты](../mfc/graphic-objects.md)

- [Одноэтапное и двухэтапное Создание графических объектов](../mfc/one-stage-and-two-stage-construction-of-objects.md)

- [Контексты устройств](../mfc/device-contexts.md)

- [Рисование в представлении](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>См. также

[Графические объекты](../mfc/graphic-objects.md)

