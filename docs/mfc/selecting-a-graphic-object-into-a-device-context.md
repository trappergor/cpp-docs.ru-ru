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
ms.openlocfilehash: 7fb1507c1200da4cdf44627557ff6993e927d51e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308536"
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
