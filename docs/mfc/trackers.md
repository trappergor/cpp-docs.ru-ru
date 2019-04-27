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
ms.openlocfilehash: b71eb0e5d46a790b01ec12f12043af783bdfcf27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62181643"
---
# <a name="trackers"></a>Средства отслеживания

[CRectTracker](../mfc/reference/crecttracker-class.md) класс предоставляет пользовательский интерфейс между прямоугольный элементами в приложении и пользователей, предоставляя широкий набор стилей отображения. Эти стили включают сплошную, штриховую или пунктирную границ; заштрихованный шаблон, который охватывает элемент; и маркеры, которые могут быть расположены снаружи или внутри границы изменения размера. Средства отслеживания часто используется в сочетании с элементами OLE, то есть объекты, производные от `COleClientItem`. Прямоугольников отслеживания предоставляют визуальные подсказки о текущем состоянии элемента.

Пример MFC OLE [OCLIENT](../overview/visual-cpp-samples.md) демонстрирует общий интерфейс, с помощью средства отслеживания и элементы клиента OLE с точки зрения приложения-контейнера. Демонстрация различных стилей и возможности объекта средство отслеживания, см. в образце общие MFC [TRACKER](../overview/visual-cpp-samples.md).

Дополнительные сведения о реализации средства отслеживания в приложении OLE, см. в разделе [средства отслеживания: Реализация средств отслеживания в приложении OLE](../mfc/trackers-implementing-trackers-in-your-ole-application.md)

## <a name="see-also"></a>См. также

[OLE](../mfc/ole-in-mfc.md)<br/>
[Класс COleClientItem](../mfc/reference/coleclientitem-class.md)
