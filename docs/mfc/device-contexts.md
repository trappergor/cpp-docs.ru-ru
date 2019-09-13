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
ms.openlocfilehash: d5337e8d8b83a641458a15612803feeec3b6361c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508661"
---
# <a name="device-contexts"></a>Контексты устройств

Контекст устройства — это структура данных Windows, содержащая сведения об атрибутах рисования устройства, таких как экран или принтер. Все вызовы рисования выполняются через объект контекста устройства, который инкапсулирует интерфейсы API Windows для рисования линий, фигур и текста. Контексты устройств допускают независящие от устройства рисунки в Windows. Контексты устройств можно использовать для рисования на экране, на принтер или в метафайл.

Объекты [кпаинтдк](../mfc/reference/cpaintdc-class.md) инкапсулируют общую идиому окон, вызывая `BeginPaint` функцию, затем рисуя в контексте устройства `EndPaint` и вызывая функцию. Конструктор вызывает метод `BeginPaint` , и деструктор вызывает `EndPaint`. `CPaintDC` Упрощенный процесс — создание объекта [CDC](../mfc/reference/cdc-class.md) , рисование, а затем уничтожение `CDC` объекта. В платформе большая часть даже этого процесса автоматизирована. В частности, `OnDraw` функция `CPaintDC` передается уже подготовленным (через `OnPrepareDC`), и вы просто рисуете в ней. Он уничтожается платформой, и контекст базового устройства освобождается в Windows после возврата из вызова `OnDraw` функции.

Объекты [кклиентдк](../mfc/reference/cclientdc-class.md) инкапсулируют работу с контекстом устройства, представляющим только клиентскую область окна. Конструктор вызывает функцию ,`ReleaseDC` и деструктор вызывает функцию. `GetDC` `CClientDC` Объекты [квиндовдк](../mfc/reference/cwindowdc-class.md) инкапсулируют контекст устройства, представляющий все окно, включая его фрейм.

[Кметафиледк](../mfc/reference/cmetafiledc-class.md) объекты инкапсулируют рисунок в метафайл Windows. В отличие от `CPaintDC` `OnDraw`переданного метода, необходимо в этом случае вызвать [онпрепаредк](../mfc/reference/cview-class.md#onpreparedc) самостоятельно.

## <a name="mouse-drawing"></a>Рисование мыши

Большинство операций рисования в программе платформы, и, таким, в большинстве случаев работы с контекстом устройства, выполняются `OnDraw` в функции-члене представления. Тем не менее вы по-прежнему можете использовать объекты контекста устройства для других целей. Например, чтобы обеспечить обратную отправку для отслеживания перемещения мыши в представлении, необходимо нарисовать непосредственно в представлении, не дожидаясь `OnDraw` вызова.

В этом случае можно использовать объект контекста устройства [кклиентдк](../mfc/reference/cclientdc-class.md) для рисования непосредственно в представлении.

### <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Контексты устройств (определение)](/windows/win32/gdi/device-contexts)

- [Рисование в представлении](../mfc/drawing-in-a-view.md)

- [Интерпретация ввода пользователя через представление](../mfc/interpreting-user-input-through-a-view.md)

- [Линии и кривые](/windows/win32/gdi/lines-and-curves)

- [Заполненные фигуры](/windows/win32/gdi/filled-shapes)

- [Шрифты и текст](/windows/win32/gdi/fonts-and-text)

- [Цвета](/windows/win32/gdi/colors)

- [Координатные пространства и преобразования](/windows/win32/gdi/coordinate-spaces-and-transformations)

## <a name="see-also"></a>См. также

[Объекты окон](../mfc/window-objects.md)
