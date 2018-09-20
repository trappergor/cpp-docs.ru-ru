---
title: Выбор графического объекта в контексте устройства | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- graphic objects [MFC], selecting into device context
- SelectObject method [MFC]
- GDI objects [MFC], device contexts
- lifetime, graphic objects [MFC]
- device contexts, selecting graphic objects into
- device contexts, graphic objects [MFC]
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 406c4e7cd87b350f9317022dcf1821fa92ddf4af
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427671"
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

