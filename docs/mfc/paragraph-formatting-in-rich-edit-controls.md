---
title: Форматирование абзацев с использованием элементов управления "Rich Edit"
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
ms.openlocfilehash: e23976e64b3c9a4a76e5b05c90d0ad033b62657a
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615339"
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Форматирование абзацев с использованием элементов управления "Rich Edit"

Функции-члены элемента управления Rich Edit ([CRichEditCtrl](reference/cricheditctrl-class.md)) можно использовать для форматирования абзацев и получения сведений о форматировании. Атрибуты форматирования абзаца включают выравнивание, табуляцию, отступы и нумерацию.

Форматирование абзаца можно применить с помощью функции члена [сетпараформат](reference/cricheditctrl-class.md#setparaformat) . Чтобы определить текущее форматирование абзаца для выделенного текста, используйте функцию члена [жетпараформат](reference/cricheditctrl-class.md#getparaformat) . Структура [формата](/windows/win32/api/richedit/ns-richedit-paraformat) с этими функциями-членами используется для указания атрибутов абзаца. Один из важных элементов **формата** \ *двмаск*. В `SetParaFormat` *двмаск* указывает, какие атрибуты абзаца будут заданы этим вызовом функции. `GetParaFormat`сообщает об атрибутах первого абзаца в выделенном фрагменте. *двмаск* задает атрибуты, согласованные по всему выбору.

## <a name="see-also"></a>См. также раздел

[Использование CRichEditCtrl](using-cricheditctrl.md)<br/>
[Элементы управления](controls-mfc.md)
