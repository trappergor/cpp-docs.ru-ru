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
ms.openlocfilehash: 095f3c15546466c6a495f6aa348990ed69b04a9e
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127370"
---
# <a name="rubber-banding-and-trackers"></a>Эластичные соединения и средства отслеживания

Другой компонент, предоставляемый с инспекторами, — это «резиновый» выбор, который позволяет пользователю выбрать несколько элементов OLE, перетащив прямоугольник изменения размера вокруг выбранных элементов. Когда пользователь отпускает левую кнопку мыши, выбираются элементы в выбранном пользователем регионе и могут управляться пользователем. Например, пользователь может перетащить выделенный фрагмент в другое приложение контейнера.

Для реализации этой функции требуется дополнительный код в функции обработчика WM_LBUTTONDOWN приложения.

В следующем примере кода реализуется выбор с резиновой полосой и дополнительные функции.

[!code-cpp[NVC_MFCOClient#6](../mfc/codesnippet/cpp/rubber-banding-and-trackers_1.cpp)]

Если вы хотите разрешить обратимую ориентацию инспектора во время использования аппаратного контроллера управления, следует вызвать [кректтраккер:: траккруббербанд](../mfc/reference/crecttracker-class.md#trackrubberband) с третьим параметром, имеющим значение **true**. Помните, что разрешение обратимой ориентации иногда приводит к тому, что [кректтраккер:: m_rect](../mfc/reference/crecttracker-class.md#m_rect) перестанет быть инвертированным. Это можно исправить с помощью вызова [крект:: нормализерект](../atl-mfc-shared/reference/crect-class.md#normalizerect).

Дополнительные сведения см. в статьях [клиентские элементы контейнера](../mfc/containers-client-items.md) и [перетаскивание OLE: Настройка перетаскивания](../mfc/drag-and-drop-ole.md#customize-drag-and-drop).

## <a name="see-also"></a>См. также раздел

[Средства отслеживания. Реализация средств отслеживания в приложении OLE](../mfc/trackers-implementing-trackers-in-your-ole-application.md)<br/>
[Класс CRectTracker](../mfc/reference/crecttracker-class.md)
