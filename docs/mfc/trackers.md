---
title: Средства отслеживания | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- trackers [MFC]
- OLE applications [MFC], trackers
- applications [OLE], trackers
- tracking OLE items [MFC]
- OLE containers [MFC], trackers
- CDC class [MFC], trackers
- CRectTracker class [MFC], implementing trackers
- OLE server applications [MFC], trackers
ms.assetid: dcd09399-6637-4621-80e5-d12670429787
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 414a7c19292e154af0b6365b766d865dca0a7dd3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439878"
---
# <a name="trackers"></a>Средства отслеживания

[CRectTracker](../mfc/reference/crecttracker-class.md) класс предоставляет пользовательский интерфейс между прямоугольный элементами в приложении и пользователей, предоставляя широкий набор стилей отображения. Эти стили включают сплошную, штриховую или пунктирную границ; заштрихованный шаблон, который охватывает элемент; и маркеры, которые могут быть расположены снаружи или внутри границы изменения размера. Средства отслеживания часто используется в сочетании с элементами OLE, то есть объекты, производные от `COleClientItem`. Прямоугольников отслеживания предоставляют визуальные подсказки о текущем состоянии элемента.

Пример MFC OLE [OCLIENT](../visual-cpp-samples.md) демонстрирует общий интерфейс, с помощью средства отслеживания и элементы клиента OLE с точки зрения приложения-контейнера. Демонстрация различных стилей и возможности объекта средство отслеживания, см. в образце общие MFC [TRACKER](../visual-cpp-samples.md).

Дополнительные сведения о реализации средства отслеживания в приложении OLE, см. в разделе [средства отслеживания: реализация средств отслеживания в OLE приложения](../mfc/trackers-implementing-trackers-in-your-ole-application.md)

## <a name="see-also"></a>См. также

[OLE](../mfc/ole-in-mfc.md)<br/>
[Класс COleClientItem](../mfc/reference/coleclientitem-class.md)
