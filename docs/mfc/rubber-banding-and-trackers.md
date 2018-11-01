---
title: Эластичные соединения и средства отслеживания
ms.date: 11/04/2016
helpviewer_keywords:
- trackers [MFC]
- CRectTracker class [MFC], implementing trackers
- OLE objects [MFC], selecting
- rubber banding [MFC]
- WM_LBUTTONDOWN [MFC]
ms.assetid: 0d0fa64c-6418-4baf-ab7f-2d16ca039230
ms.openlocfilehash: f15256f99a744273b3487925bf273ad563c32aff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50450808"
---
# <a name="rubber-banding-and-trackers"></a>Эластичные соединения и средства отслеживания

Еще одна функция, в состав средства отслеживания является выбор «изменяемый», который позволяет пользователю выбирать несколько элементов OLE растягивая прямоугольник вокруг элементов для выбора размера. Когда пользователь отпускает левую кнопку мыши, элементы в пределах региона, выбранного пользователем выбраны и могут управляться пользователем. К примеру пользователь может перетаскивать выделения в другое приложение контейнера.

Для реализации этой функции требуется дополнительный код в функции обработчика WM_LBUTTONDOWN вашего приложения.

В следующем образце кода реализует Выбор эластичного и дополнительные функции.

[!code-cpp[NVC_MFCOClient#6](../mfc/codesnippet/cpp/rubber-banding-and-trackers_1.cpp)]

Если вы хотите разрешить обратимое ориентацию объекта отслеживания во время эластичные соединения, необходимо вызвать [CRectTracker::TrackRubberBand](../mfc/reference/crecttracker-class.md#trackrubberband) с указанием третьего параметра равным **TRUE**. Помните, что обратимое ориентации, иногда вызывает [CRectTracker::m_rect](../mfc/reference/crecttracker-class.md#m_rect) чтобы стать обращена. Это можно исправить путем вызова [CRect::NormalizeRect](../atl-mfc-shared/reference/crect-class.md#normalizerect).

Дополнительные сведения см. в разделе [элементы клиента контейнера](../mfc/containers-client-items.md) и [Настройка перетаскивания](../mfc/drag-and-drop-customizing.md).

## <a name="see-also"></a>См. также

[Средства отслеживания. Реализация средств отслеживания в приложении OLE](../mfc/trackers-implementing-trackers-in-your-ole-application.md)<br/>
[Класс CRectTracker](../mfc/reference/crecttracker-class.md)
