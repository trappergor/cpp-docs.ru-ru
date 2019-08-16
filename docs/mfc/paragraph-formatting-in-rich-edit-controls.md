---
title: Форматирование абзацев с использованием элементов управления "Rich Edit"
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
ms.openlocfilehash: f2ac69838bf39afb636c3d41c97adc1378463d1b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507979"
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Форматирование абзацев с использованием элементов управления "Rich Edit"

Функции-члены элемента управления Rich Edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) можно использовать для форматирования абзацев и получения сведений о форматировании. Атрибуты форматирования абзаца включают выравнивание, табуляцию, отступы и нумерацию.

Форматирование абзаца можно применить с помощью функции члена [сетпараформат](../mfc/reference/cricheditctrl-class.md#setparaformat) . Чтобы определить текущее форматирование абзаца для выделенного текста, используйте функцию члена [жетпараформат](../mfc/reference/cricheditctrl-class.md#getparaformat) . Структура [формата](/windows/win32/api/richedit/ns-richedit-paraformat) с этими функциями-членами используется для указания атрибутов абзаца. Один из важных элементов **формата** \ *двмаск*. В `SetParaFormat` *двмаск* указывает, какие атрибуты абзаца будут заданы этим вызовом функции. `GetParaFormat`сообщает об атрибутах первого абзаца в выделенном фрагменте. *двмаск* задает атрибуты, согласованные по всему выбору.

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
