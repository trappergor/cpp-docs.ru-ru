---
title: Средства отслеживания
ms.date: 11/04/2016
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
ms.openlocfilehash: 74e70f989d3803b11f05150f9b55c6dfe79ed876
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481956"
---
# <a name="trackers"></a>Средства отслеживания

[CRectTracker](../mfc/reference/crecttracker-class.md) класс предоставляет пользовательский интерфейс между прямоугольный элементами в приложении и пользователей, предоставляя широкий набор стилей отображения. Эти стили включают сплошную, штриховую или пунктирную границ; заштрихованный шаблон, который охватывает элемент; и маркеры, которые могут быть расположены снаружи или внутри границы изменения размера. Средства отслеживания часто используется в сочетании с элементами OLE, то есть объекты, производные от `COleClientItem`. Прямоугольников отслеживания предоставляют визуальные подсказки о текущем состоянии элемента.

Пример MFC OLE [OCLIENT](../visual-cpp-samples.md) демонстрирует общий интерфейс, с помощью средства отслеживания и элементы клиента OLE с точки зрения приложения-контейнера. Демонстрация различных стилей и возможности объекта средство отслеживания, см. в образце общие MFC [TRACKER](../visual-cpp-samples.md).

Дополнительные сведения о реализации средства отслеживания в приложении OLE, см. в разделе [средства отслеживания: реализация средств отслеживания в OLE приложения](../mfc/trackers-implementing-trackers-in-your-ole-application.md)

## <a name="see-also"></a>См. также

[OLE](../mfc/ole-in-mfc.md)<br/>
[Класс COleClientItem](../mfc/reference/coleclientitem-class.md)
