---
title: Форматирование абзацев с использованием элементов управления "Rich Edit"
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
ms.openlocfilehash: baee4863bee9b96e7a850e70b8f13388f69b41cf
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57285234"
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Форматирование абзацев с использованием элементов управления "Rich Edit"

Можно использовать функции-члены элемента управления форматированным редактированием ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) для форматирования абзацев и получить сведения о форматировании. Атрибуты форматирования абзаца включают выравнивание, вкладки, отступы и нумерации.

Можно применить форматирование абзаца, с помощью [SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat) функция-член. Чтобы определить текущий абзац, форматирование для выделенного текста, используйте [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat) функция-член. [PARAFORMAT](/windows/desktop/api/richedit/ns-richedit-_paraformat) структура будет использована в эти функции-члены для задания атрибутов абзаца. Один из важные члены **PARAFORMAT** — *dwMask*. В `SetParaFormat`, *dwMask* указывает, какие атрибуты абзаца установит этим вызовом функции. `GetParaFormat` Выводит атрибуты в первый абзац Выбор; *dwMask* указывает атрибуты, которые они единообразны во всем выделения.

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
