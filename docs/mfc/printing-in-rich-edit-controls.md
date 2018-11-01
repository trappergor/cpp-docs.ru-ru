---
title: Печать в элементах управления "Rich Edit"
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC], CRichEditCtrl
- rich edit controls [MFC], printing
- CRichEditCtrl class [MFC], printing
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
ms.openlocfilehash: bf402f5495ad85eb0c5067d60fcedfe29e6350bb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641211"
---
# <a name="printing-in-rich-edit-controls"></a>Печать в элементах управления "Rich Edit"

Чтобы узнать, элемент управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) для подготовки к просмотру выходные данные для заданного устройства, такие как принтер. Можно также указать, что устройство вывода, для которого элемент управления rich edit форматирует его текст.

Чтобы форматировать часть содержимого элемента управления "rich edit" для конкретного устройства, можно использовать [FormatRange](../mfc/reference/cricheditctrl-class.md#formatrange) функция-член. [FORMATRANGE](/windows/desktop/api/richedit/ns-richedit-_formatrange) структура, используемая с этой функцией указывает диапазон текста для форматирования, а также контекст устройства (DC) для целевого устройства.

После форматирования текста для вывода устройства, можно отправлять выходные данные на устройстве с помощью [DisplayBand](../mfc/reference/cricheditctrl-class.md#displayband) функция-член. С помощью многократно `FormatRange` и `DisplayBand`, приложение, которое выводит содержимое элемента управления форматированным редактированием можно реализовать чередование. (Чередования — деление на более мелкие части выходных данных для печати).

Можно использовать [SetTargetDevice](../mfc/reference/cricheditctrl-class.md#settargetdevice) функции-члена для указания целевого устройства, для которого элемент управления rich edit форматирует его текст. Эта функция полезна для WYSIWYG (очевидно, что вы получаете) форматирование, в котором приложение размещает текст с помощью метрик шрифтов принтер по умолчанию вместо экрана.

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

