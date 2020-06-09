---
title: Классы вывода (контекст устройства)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.output
helpviewer_keywords:
- device contexts [MFC], classes
- screen output classes [MFC]
- printing classes [MFC]
- window drawing classes [MFC]
- painting classes [MFC]
- output classes [MFC]
ms.assetid: 35fd6435-a38e-42c6-a3fa-cd6f39370fc3
ms.openlocfilehash: b15f5034604f9d6b67574288140b79b144692478
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615364"
---
# <a name="output-device-context-classes"></a>Классы вывода (контекст устройства)

Эти классы инкапсулируют различные типы контекстов устройств, доступные в Windows.

Большинство из следующих классов инкапсулируют маркер в контекст устройства Windows. Контекст устройства — это объект Windows, который содержит сведения об атрибутах рисования устройства, такого как экран или принтер. Все вызовы рисования выполняются через объект контекста устройства. Дополнительные классы, производные от `CDC` инкапсуляции специализированной функциональности контекста устройства, включая поддержку метафайлов Windows.

[CDC](reference/cdc-class.md)<br/>
Базовый класс для контекстов устройств. Используется непосредственно для доступа ко всему отображению и для доступа к неотображаемым контекстам, таким как принтеры.

[CPaintDC](reference/cpaintdc-class.md)<br/>
Контекст вывода, используемый в `OnPaint` функциях-членах Windows. Автоматически вызывает `BeginPaint` при создании и `EndPaint` уничтожении.

[CClientDC](reference/cclientdc-class.md)<br/>
Контекст вывода для клиентских областей окон. Используется, например, для отрисовки мгновенного ответа на события мыши.

[CWindowDC](reference/cwindowdc-class.md)<br/>
Контекст вывода для всех окон, включая клиентские и неклиентские области.

[CMetaFileDC](reference/cmetafiledc-class.md)<br/>
Контекст устройства для метафайлов Windows. Метафайл Windows содержит последовательность команд интерфейса графических устройств (GDI), которые можно воспроизвести для создания образа. Вызовы функций-членов в `CMetaFileDC` записываются в метафайл.

## <a name="related-classes"></a>Связанные классы

[CPoint](../atl-mfc-shared/reference/cpoint-class.md)<br/>
Содержит координаты координат (x, y).

[CSize](../atl-mfc-shared/reference/csize-class.md)<br/>
Удерживает расстояние, относительное положение или парные значения.

[CRect](../atl-mfc-shared/reference/crect-class.md)<br/>
Содержит координаты прямоугольных областей.

[CRgn](reference/crgn-class.md)<br/>
Инкапсулирует область GDI для манипулирования эллиптической, многоугольной или неравномерной области внутри окна. Используется в сочетании с функциями обрезкиных элементов в классе `CDC` .

[CRectTracker](reference/crecttracker-class.md)<br/>
Отображает и обрабатывает пользовательский интерфейс для изменения размера и перемещения прямоугольных объектов.

[CColorDialog](reference/ccolordialog-class.md)<br/>
Предоставляет стандартное диалоговое окно для выбора цвета.

[CFontDialog](reference/cfontdialog-class.md)<br/>
Предоставляет стандартное диалоговое окно для выбора шрифта.

[CPrintDialog](reference/cprintdialog-class.md)<br/>
Предоставляет стандартное диалоговое окно для печати файла.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](class-library-overview.md)
