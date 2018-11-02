---
title: Контексты устройств
ms.date: 11/04/2016
helpviewer_keywords:
- OnPrepareDC method [MFC]
- windows [MFC], and device context
- drawing [MFC], device context
- CClientDC class [MFC], and GetDC method [MFC]
- drawing [MFC], in mouse and device contexts
- CDC class [MFC], objects
- device contexts [MFC]
- client areas
- CMetaFileDC class [MFC], and OnPrepareDC method [MFC]
- GDI objects [MFC], device contexts
- graphic objects [MFC], device contexts
- frame windows [MFC], device contexts
- metafiles and device contexts
- EndPaint method [MFC]
- printers [MFC], device contexts
- mouse [MFC], drawing and device contexts
- BeginPaint method, CPaintDC
- CPaintDC class [MFC], device context for painting
- windows [MFC], drawing directly into
- client areas, and device context
- device contexts [MFC], CDC class [MFC]
- user interface [MFC], device contexts
- device-independent drawing
- GetDC method and CClientDC class [MFC]
- CClientDC class [MFC], and ReleaseDC method [MFC]
- ReleaseDC method [MFC]
- device contexts [MFC], about device contexts
- drawing [MFC], directly into windows
- painting and device context
ms.assetid: d0cd51f1-f778-4c7e-bf50-d738d10433c7
ms.openlocfilehash: 8eca18795fac96e5cbddb404b901eb35da2de4b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585982"
---
# <a name="device-contexts"></a>Контексты устройств

Контекст устройства — это структура данных Windows, содержащий сведения о атрибутов рисования устройства, такие как экран или принтер. Все вызовы рисования выполняются через объект контекста устройства, который инкапсулирует API-интерфейсы Windows для рисования линий, фигур и текста. Контексты устройств позволяют аппаратно независимое рисование в Windows. Контексты устройств можно использовать для рисования на экране, на принтер или в метафайл.

[CPaintDC](../mfc/reference/cpaintdc-class.md) объектов инкапсулировать распространенных случаях Windows, вызвав `BeginPaint` функции, а затем рисование в контексте устройства, то при вызове `EndPaint` функции. `CPaintDC` Конструктор вызывает `BeginPaint` для вас и деструктор вызывает `EndPaint`. Упрощенный процесс является создание [CDC](../mfc/reference/cdc-class.md) объекта, рисования и затем удалите `CDC` объекта. В платформе большая часть даже этот процесс выполняется автоматически. В частности ваш `OnDraw` функции передается `CPaintDC` уже подготовлен (через `OnPrepareDC`), и вы просто привлечь в него. Он будет уничтожен платформой и базовый контекст устройства будет выпущено как Windows при возврате из вызова вашего `OnDraw` функции.

[CClientDC](../mfc/reference/cclientdc-class.md) объектов инкапсулировать работу с контекста устройства, представляющий только клиентскую область окна. `CClientDC` Конструктор вызывает `GetDC` функции и вызовы деструктора `ReleaseDC` функции. [CWindowDC](../mfc/reference/cwindowdc-class.md) объектов инкапсулировать контекста устройства, представляющий всего окна, включая фрейма.

[CMetaFileDC](../mfc/reference/cmetafiledc-class.md) объектов инкапсулировать рисование в метафайл Windows. В отличие от к `CPaintDC` передается `OnDraw`, в этом случае необходимо вызвать [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) самостоятельно.

## <a name="mouse-drawing"></a>Рисование мыши

Большинство рисования в приложении framework — и тем самым большую часть работы контекста устройства, выполняется в режиме `OnDraw` функция-член. Тем не менее объекты контекста устройства по-прежнему можно использовать для других целей. Например, чтобы отправить отзыв отслеживания для перемещения указателя мыши в представлении, необходимо рисовать непосредственно в представление, не дожидаясь `OnDraw` для вызова.

В этом случае можно использовать [CClientDC](../mfc/reference/cclientdc-class.md) объект контекста устройства для рисования непосредственно в представление.

### <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Контексты устройств (определение)](https://msdn.microsoft.com/library/windows/desktop/dd183553)

- [Рисование в представлении](../mfc/drawing-in-a-view.md)

- [Интерпретация ввода пользователя через представление](../mfc/interpreting-user-input-through-a-view.md)

- [Линии и кривые](https://msdn.microsoft.com/library/windows/desktop/dd145028)

- [Закрашенные фигуры](https://msdn.microsoft.com/library/windows/desktop/dd162714)

- [Шрифты и текст](/windows/desktop/gdi/fonts-and-text)

- [Цвета](https://msdn.microsoft.com/library/windows/desktop/dd183450)

- [Координат и преобразования](https://msdn.microsoft.com/library/windows/desktop/dd183475)

## <a name="see-also"></a>См. также

[Объекты окон](../mfc/window-objects.md)

