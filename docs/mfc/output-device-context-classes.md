---
title: Выходные данные классы (контекст устройства) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.output
dev_langs:
- C++
helpviewer_keywords:
- device contexts [MFC], classes
- screen output classes [MFC]
- printing classes [MFC]
- window drawing classes [MFC]
- painting classes [MFC]
- output classes [MFC]
ms.assetid: 35fd6435-a38e-42c6-a3fa-cd6f39370fc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 40b1406e8c788554d549ee1bdaa1adc21070d994
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373559"
---
# <a name="output-device-context-classes"></a>Классы вывода (контекст устройства)

Эти классы инкапсулируют различных типов устройств контексты, доступные в Windows.

Большая часть следующие классы инкапсулируют дескриптор контекста устройства Windows. Контекст устройства — объект Windows, который содержит сведения о атрибутов рисования устройство, такое как экран или принтер. Все вызовы рисования выполняются через объект контекста устройства. Дополнительные классы, производные от `CDC` инкапсулируют функциональность специализированные контекста устройства, включая поддержку метафайлы Windows.

[CDC](../mfc/reference/cdc-class.md)<br/>
Базовый класс для контексты устройств. Использовать непосредственно для доступа к целой отображаемой и для доступа к nondisplay контекстах, например принтеры.

[CPaintDC](../mfc/reference/cpaintdc-class.md)<br/>
Контекста отображения, используемых в `OnPaint` функции-члены из windows. Автоматически вызывает `BeginPaint` на построение и `EndPaint` при уничтожении объекта.

[CClientDC](../mfc/reference/cclientdc-class.md)<br/>
Контекст отображения для области клиента windows. Используется, например, для рисования в немедленный ответ на события мыши.

[CWindowDC](../mfc/reference/cwindowdc-class.md)<br/>
Контекст отображения для всего windows, включая клиентские и неклиентские области.

[CMetaFileDC](../mfc/reference/cmetafiledc-class.md)<br/>
Контекст устройства метафайлов Windows. Метафайл Windows содержит последовательность графических устройств (интерфейс) команд, которые могут быть воспроизведены для создания образа. Вызовы к функции-члены `CMetaFileDC` записываются в метафайл.

## <a name="related-classes"></a>Связанные классы

[CPoint](../atl-mfc-shared/reference/cpoint-class.md)<br/>
Содержит пары координат (x, y).

[CSize](../atl-mfc-shared/reference/csize-class.md)<br/>
Содержит расстояние, относительные позиции или пар значений.

[CRect](../atl-mfc-shared/reference/crect-class.md)<br/>
Содержит координаты прямоугольной области.

[CRgn](../mfc/reference/crgn-class.md)<br/>
Инкапсулирует область GDI для манипулирования эллиптической кусочно-линейной и нестандартные область в пределах этого периода. Используется в сочетании с обрезки функции-члены в классе `CDC`.

[CRectTracker](../mfc/reference/crecttracker-class.md)<br/>
Отображает и обрабатывает пользовательский интерфейс для изменения размеров и перемещение объектов прямоугольной.

[CColorDialog](../mfc/reference/ccolordialog-class.md)<br/>
Предоставляет стандартное диалоговое окно для выбора цвета.

[CFontDialog](../mfc/reference/cfontdialog-class.md)<br/>
Предоставляет стандартное диалоговое окно для выбора шрифта.

[CPrintDialog](../mfc/reference/cprintdialog-class.md)<br/>
Предоставляет стандартное диалоговое окно для печати файла.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)

